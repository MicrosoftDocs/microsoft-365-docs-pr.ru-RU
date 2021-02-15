---
title: Создание записей DNS для Dyn.com Майкрософт
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Dyn.com for Microsoft.
ms.openlocfilehash: d1b77d6b4f38dd3e0979f448a77b293564841f45
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657940"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="94b45-103">Создание записей DNS для Dyn.com Майкрософт</span><span class="sxs-lookup"><span data-stu-id="94b45-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="94b45-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="94b45-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="94b45-105">Если Dyn.com ваш поставщик услуг размещения DNS, выполните действия, которые необходимо в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="94b45-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="94b45-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94b45-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="94b45-109">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="94b45-109">Add a TXT record for verification</span></span>
<span data-ttu-id="94b45-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="94b45-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="94b45-p102">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="94b45-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="94b45-114">На странице **"Службы уровня зоны"** выберите **Dyn Standard DNS Service** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="94b45-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="94b45-115">На странице **DNS для** домена выберите **параметры.**</span><span class="sxs-lookup"><span data-stu-id="94b45-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="94b45-116">Выберите **"Включить интерфейс эксперта".**</span><span class="sxs-lookup"><span data-stu-id="94b45-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="94b45-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="94b45-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94b45-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="94b45-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="94b45-119">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="94b45-119">**Host**</span></span>|<span data-ttu-id="94b45-120">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="94b45-120">**TTL**</span></span>|<span data-ttu-id="94b45-121">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="94b45-121">**Type**</span></span>|<span data-ttu-id="94b45-122">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="94b45-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94b45-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="94b45-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="94b45-124">600</span><span class="sxs-lookup"><span data-stu-id="94b45-124">600</span></span>  <br/> |<span data-ttu-id="94b45-125">TXT</span><span class="sxs-lookup"><span data-stu-id="94b45-125">TXT</span></span>  <br/> |<span data-ttu-id="94b45-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="94b45-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="94b45-127">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="94b45-127">**Note:** This is an example.</span></span> <span data-ttu-id="94b45-128">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="94b45-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="94b45-129">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="94b45-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="94b45-131">Выберите **"Создать запись"**.</span><span class="sxs-lookup"><span data-stu-id="94b45-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="94b45-133">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="94b45-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="94b45-134">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="94b45-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="94b45-135">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="94b45-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="94b45-136">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="94b45-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="94b45-137">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="94b45-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="94b45-138">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="94b45-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="94b45-139">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="94b45-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="94b45-p104">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94b45-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="94b45-143">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94b45-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="94b45-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="94b45-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="94b45-p105">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="94b45-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="94b45-148">На странице **"Службы уровня зоны"** выберите **Dyn Standard DNS Service** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="94b45-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="94b45-149">На странице DNS для домена выберите **параметры.**</span><span class="sxs-lookup"><span data-stu-id="94b45-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="94b45-150">Выберите **"Включить интерфейс эксперта".**</span><span class="sxs-lookup"><span data-stu-id="94b45-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="94b45-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="94b45-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94b45-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="94b45-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="94b45-153">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="94b45-153">**Host**</span></span>|<span data-ttu-id="94b45-154">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="94b45-154">**TTL**</span></span>|<span data-ttu-id="94b45-155">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="94b45-155">**Type**</span></span>|<span data-ttu-id="94b45-156">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="94b45-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94b45-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="94b45-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="94b45-158">600</span><span class="sxs-lookup"><span data-stu-id="94b45-158">600</span></span>  <br/> |<span data-ttu-id="94b45-159">MX</span><span class="sxs-lookup"><span data-stu-id="94b45-159">MX</span></span>  <br/> |<span data-ttu-id="94b45-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="94b45-161">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="94b45-p106">**10**  значение приоритета MX. Добавьте его в начало значения MX, отделив от остальной части пробелом.  </span><span class="sxs-lookup"><span data-stu-id="94b45-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="94b45-164">**Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94b45-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="94b45-165">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="94b45-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="94b45-166">Дополнительные сведения о приоритете см. в статье [Что такое приоритет записей MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="94b45-166">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="94b45-168">Выберите **"Создать запись"**.</span><span class="sxs-lookup"><span data-stu-id="94b45-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="94b45-170">Если есть какие-либо другие записи MX, удалите их, выбрав для каждой записи в столбце **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="94b45-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="94b45-172">Выберите **"Применить изменения".**</span><span class="sxs-lookup"><span data-stu-id="94b45-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="94b45-174">Добавьте шесть записей CNAME, необходимых для Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="94b45-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="94b45-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="94b45-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="94b45-p108">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="94b45-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="94b45-179">На странице **"Службы уровня зоны"** выберите **Dyn Standard DNS Service** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="94b45-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="94b45-180">На странице **DNS для** домена выберите **параметры.**</span><span class="sxs-lookup"><span data-stu-id="94b45-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="94b45-181">Выберите **"Включить интерфейс эксперта".**</span><span class="sxs-lookup"><span data-stu-id="94b45-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="94b45-182">Добавьте первую из шести записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="94b45-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="94b45-183">В поля для новой записи в разделе "Добавление записи **DNS"** введите (или скопируйте и введите) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="94b45-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="94b45-184">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="94b45-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="94b45-185">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="94b45-185">**Host**</span></span>|<span data-ttu-id="94b45-186">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="94b45-186">**TTL**</span></span>|<span data-ttu-id="94b45-187">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="94b45-187">**Type**</span></span>|<span data-ttu-id="94b45-188">**Data** (Данные)</span><span class="sxs-lookup"><span data-stu-id="94b45-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94b45-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="94b45-189">autodiscover</span></span>  <br/> |<span data-ttu-id="94b45-190">600</span><span class="sxs-lookup"><span data-stu-id="94b45-190">600</span></span>  <br/> |<span data-ttu-id="94b45-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="94b45-191">CNAME</span></span>  <br/> |<span data-ttu-id="94b45-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="94b45-193">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="94b45-194">sip</span><span class="sxs-lookup"><span data-stu-id="94b45-194">sip</span></span>  <br/> |<span data-ttu-id="94b45-195">600</span><span class="sxs-lookup"><span data-stu-id="94b45-195">600</span></span>  <br/> |<span data-ttu-id="94b45-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="94b45-196">CNAME</span></span>  <br/> |<span data-ttu-id="94b45-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="94b45-198">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="94b45-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="94b45-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="94b45-200">600</span><span class="sxs-lookup"><span data-stu-id="94b45-200">600</span></span>  <br/> |<span data-ttu-id="94b45-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="94b45-201">CNAME</span></span>  <br/> |<span data-ttu-id="94b45-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="94b45-203">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="94b45-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="94b45-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="94b45-205">600</span><span class="sxs-lookup"><span data-stu-id="94b45-205">600</span></span>  <br/> |<span data-ttu-id="94b45-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="94b45-206">CNAME</span></span>  <br/> |<span data-ttu-id="94b45-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="94b45-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="94b45-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="94b45-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="94b45-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="94b45-210">600</span><span class="sxs-lookup"><span data-stu-id="94b45-210">600</span></span>  <br/> |<span data-ttu-id="94b45-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="94b45-211">CNAME</span></span>  <br/> |<span data-ttu-id="94b45-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="94b45-213">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="94b45-215">Выберите **"Создать запись"**.</span><span class="sxs-lookup"><span data-stu-id="94b45-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="94b45-217">Добавьте оставшиеся пять записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="94b45-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="94b45-218">В разделе **"Добавление записи DNS"** создайте запись, используя значения из следующей  строки таблицы, а затем снова выберите "Создать запись", чтобы завершить запись.</span><span class="sxs-lookup"><span data-stu-id="94b45-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="94b45-219">Повторяйте эти действия, пока не будут созданы все шесть записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="94b45-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="94b45-220">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="94b45-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="94b45-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="94b45-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="94b45-222">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="94b45-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="94b45-223">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="94b45-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="94b45-224">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94b45-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="94b45-225">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="94b45-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="94b45-p110">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/). Сначала вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="94b45-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="94b45-229">На странице **"Службы уровня зоны"** выберите **Dyn Standard DNS Service** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="94b45-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="94b45-230">На странице **DNS для** домена выберите **параметры.**</span><span class="sxs-lookup"><span data-stu-id="94b45-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="94b45-231">Выберите **"Включить интерфейс эксперта".**</span><span class="sxs-lookup"><span data-stu-id="94b45-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="94b45-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="94b45-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="94b45-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="94b45-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="94b45-234">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="94b45-234">**Host**</span></span>|<span data-ttu-id="94b45-235">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="94b45-235">**TTL**</span></span>|<span data-ttu-id="94b45-236">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="94b45-236">**Type**</span></span>|<span data-ttu-id="94b45-237">**Data (Данные)**</span><span class="sxs-lookup"><span data-stu-id="94b45-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94b45-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="94b45-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="94b45-239">600</span><span class="sxs-lookup"><span data-stu-id="94b45-239">600</span></span>  <br/> |<span data-ttu-id="94b45-240">TXT</span><span class="sxs-lookup"><span data-stu-id="94b45-240">TXT</span></span>  <br/> |<span data-ttu-id="94b45-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="94b45-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="94b45-242">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="94b45-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="94b45-244">Выберите **"Создать запись"**.</span><span class="sxs-lookup"><span data-stu-id="94b45-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="94b45-246">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="94b45-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="94b45-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="94b45-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="94b45-248">Чтобы приступить к работе, откройте страницу со своими доменами на сайте Dyn.com по [этой ссылке](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="94b45-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="94b45-249">Сначала вам будет предложено войти в систему</span><span class="sxs-lookup"><span data-stu-id="94b45-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="94b45-251">На странице **"Службы уровня зоны"** выберите **Dyn Standard DNS Service** для домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="94b45-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="94b45-252">На странице **DNS для** домена выберите **параметры.**</span><span class="sxs-lookup"><span data-stu-id="94b45-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="94b45-253">Выберите **"Включить интерфейс эксперта".**</span><span class="sxs-lookup"><span data-stu-id="94b45-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="94b45-254">Добавьте первую из двух записей SRV.</span><span class="sxs-lookup"><span data-stu-id="94b45-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="94b45-255">В поля для новой записи в разделе "Добавление записи **DNS"** введите (или скопируйте и введите) значения из первой строки таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="94b45-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="94b45-256">В раскрывающемся списке выберите значение параметра **Type** (Тип).</span><span class="sxs-lookup"><span data-stu-id="94b45-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="94b45-257">**Host (Узел)**</span><span class="sxs-lookup"><span data-stu-id="94b45-257">**Host**</span></span>|<span data-ttu-id="94b45-258">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="94b45-258">**TTL**</span></span>|<span data-ttu-id="94b45-259">**Type (Тип)**</span><span class="sxs-lookup"><span data-stu-id="94b45-259">**Type**</span></span>|<span data-ttu-id="94b45-260">**Данные**</span><span class="sxs-lookup"><span data-stu-id="94b45-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94b45-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="94b45-261">_sip._tls</span></span>|<span data-ttu-id="94b45-262">600</span><span class="sxs-lookup"><span data-stu-id="94b45-262">600</span></span>|<span data-ttu-id="94b45-263">SRV</span><span class="sxs-lookup"><span data-stu-id="94b45-263">SRV</span></span>|<span data-ttu-id="94b45-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="94b45-265">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="94b45-266">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="94b45-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="94b45-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="94b45-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="94b45-268">600</span><span class="sxs-lookup"><span data-stu-id="94b45-268">600</span></span>|<span data-ttu-id="94b45-269">SRV</span><span class="sxs-lookup"><span data-stu-id="94b45-269">SRV</span></span>|<span data-ttu-id="94b45-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="94b45-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="94b45-271">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="94b45-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="94b45-272">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="94b45-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="94b45-274">Выберите **"Создать запись"**.</span><span class="sxs-lookup"><span data-stu-id="94b45-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="94b45-276">Добавьте вторую запись SRV.</span><span class="sxs-lookup"><span data-stu-id="94b45-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="94b45-277">В разделе **"Добавление записи DNS"** создайте запись, используя значения из второй  строки таблицы, а затем снова выберите "Создать запись", чтобы завершить запись.</span><span class="sxs-lookup"><span data-stu-id="94b45-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="94b45-p114">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94b45-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
