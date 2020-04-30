---
title: Создание записей DNS на сайте Netregistry для Майкрософт
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу Netregistry для Майкрософт.
ms.openlocfilehash: ed3e3bae232dcbb3c8e4eea3d1a3bc4dd0a88799
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939159"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="57d93-103">Создание записей DNS на сайте Netregistry для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="57d93-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="57d93-104">Если вы не нашли нужную информацию, см. статью [Вопросы и ответы о доменах](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="57d93-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="57d93-105">Если ваш поставщик услуг размещения DNS  Netregistry, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб.</span><span class="sxs-lookup"><span data-stu-id="57d93-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="57d93-106">Ниже перечислены основные записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="57d93-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="57d93-107">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="57d93-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="57d93-108">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57d93-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="57d93-109">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="57d93-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="57d93-110">Добавление записи TXT для SPF, чтобы предотвратить получение нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="57d93-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="57d93-111">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="57d93-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="57d93-112">Когда вы добавите эти записи на сайте Netregistry, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57d93-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="57d93-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57d93-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="57d93-116">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="57d93-116">Add a TXT record for verification</span></span>
<span data-ttu-id="57d93-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="57d93-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="57d93-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="57d93-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57d93-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="57d93-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="57d93-p104">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57d93-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="57d93-125">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="57d93-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="57d93-127">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="57d93-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="57d93-129">В разделе **Добавление записи зоны**выберите **запись TXT** в списке, а затем выберите **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="57d93-131">Перед и после записи в поле TXT необходимо использовать кавычки.</span><span class="sxs-lookup"><span data-stu-id="57d93-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="57d93-132">В форме **New TXT Record** (Новая запись типа TXT) введите (или скопируйте и вставьте) значения из следующей таблицы:</span><span class="sxs-lookup"><span data-stu-id="57d93-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="57d93-133">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="57d93-133">**Name**</span></span>|<span data-ttu-id="57d93-134">**TTL (SEC) (Срок жизни в секундах)**</span><span class="sxs-lookup"><span data-stu-id="57d93-134">**TTL (SEC)**</span></span>|<span data-ttu-id="57d93-135">**TXT (Адрес "указывает на" или значение)**</span><span class="sxs-lookup"><span data-stu-id="57d93-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57d93-136">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="57d93-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="57d93-137">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-138">"MS = Мскскскскскскскскс"</span><span class="sxs-lookup"><span data-stu-id="57d93-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="57d93-139">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="57d93-139">**Note:** This is an example.</span></span> <span data-ttu-id="57d93-140">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="57d93-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="57d93-141">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="57d93-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="57d93-143">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-143">Select **Add record**.</span></span>
    
<span data-ttu-id="57d93-144">Теперь, когда запись добавлена на веб-сайт регистратора доменных имен, вернитесь в продукт корпорации Майкрософт и запросите эту запись.</span><span class="sxs-lookup"><span data-stu-id="57d93-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="57d93-145">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="57d93-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="57d93-146">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="57d93-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="57d93-147">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="57d93-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="57d93-148">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="57d93-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="57d93-149">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="57d93-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="57d93-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57d93-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="57d93-153">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57d93-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="57d93-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="57d93-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="57d93-p107">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57d93-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="57d93-158">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="57d93-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="57d93-160">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="57d93-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="57d93-162">В разделе **текущие записи зоны**удалите записи MX по умолчанию, нажав кнопку **Удалить** рядом с каждой записью MX в списке.</span><span class="sxs-lookup"><span data-stu-id="57d93-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="57d93-164">В разделе **Добавление записи зоны**выберите **запись MX** в списке, а затем выберите **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="57d93-166">В **новой форме MX Record (запись MX** ) введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="57d93-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="57d93-167">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="57d93-167">**Name**</span></span>|<span data-ttu-id="57d93-168">**TTL (SEC) (Срок жизни в секундах)**</span><span class="sxs-lookup"><span data-stu-id="57d93-168">**TTL (SEC)**</span></span>|<span data-ttu-id="57d93-169">**Exchange (указывает на адрес или значение)**</span><span class="sxs-lookup"><span data-stu-id="57d93-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="57d93-170">**Является полным узлом?**</span><span class="sxs-lookup"><span data-stu-id="57d93-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="57d93-171">**Предпочтения (приоритет)**</span><span class="sxs-lookup"><span data-stu-id="57d93-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57d93-172">(оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="57d93-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="57d93-173">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="57d93-174">*\<ключ_домена\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="57d93-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="57d93-175">**Примечание:** Получите \* \<ключ\> домена\* из учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57d93-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="57d93-176">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="57d93-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="57d93-177">(установите флажок)</span><span class="sxs-lookup"><span data-stu-id="57d93-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="57d93-178">10 </span><span class="sxs-lookup"><span data-stu-id="57d93-178">10</span></span>  <br/> <span data-ttu-id="57d93-179">For more information about priority, see What is MX priority?</span><span class="sxs-lookup"><span data-stu-id="57d93-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="57d93-181">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="57d93-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="57d93-183">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="57d93-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="57d93-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="57d93-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="57d93-p109">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57d93-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="57d93-188">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="57d93-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="57d93-190">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="57d93-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="57d93-192">В разделе **Добавление записи зоны**выберите **запись CNAME** в списке и нажмите кнопку **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="57d93-194">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="57d93-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="57d93-195">**Имя**</span><span class="sxs-lookup"><span data-stu-id="57d93-195">**Name**</span></span>|<span data-ttu-id="57d93-196">**Тип**</span><span class="sxs-lookup"><span data-stu-id="57d93-196">**Type**</span></span>|<span data-ttu-id="57d93-197">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="57d93-197">**TTL**</span></span>|<span data-ttu-id="57d93-198">**УЗЕЛ (значение "точка" или "адрес")**</span><span class="sxs-lookup"><span data-stu-id="57d93-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57d93-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="57d93-199">autodiscover</span></span>  <br/> |<span data-ttu-id="57d93-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="57d93-200">CNAME</span></span>  <br/> |<span data-ttu-id="57d93-201">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="57d93-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="57d93-203">sip</span><span class="sxs-lookup"><span data-stu-id="57d93-203">sip</span></span>  <br/> |<span data-ttu-id="57d93-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="57d93-204">CNAME</span></span>  <br/> |<span data-ttu-id="57d93-205">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57d93-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57d93-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="57d93-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="57d93-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="57d93-208">CNAME</span></span>  <br/> |<span data-ttu-id="57d93-209">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57d93-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57d93-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="57d93-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="57d93-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="57d93-212">CNAME</span></span>  <br/> |<span data-ttu-id="57d93-213">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="57d93-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="57d93-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="57d93-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="57d93-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="57d93-216">CNAME</span></span>  <br/> |<span data-ttu-id="57d93-217">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="57d93-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="57d93-220">Нажмите кнопку **Добавить запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="57d93-222">Повторив эти действия, создайте пять других записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="57d93-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="57d93-223">Создайте пять других записей CNAME, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="57d93-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="57d93-224">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="57d93-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="57d93-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="57d93-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="57d93-226">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="57d93-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="57d93-227">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="57d93-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="57d93-228">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57d93-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="57d93-229">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="57d93-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="57d93-p111">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57d93-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="57d93-233">Рядом с нужным доменом щелкните ссылку **Manage** (Управление).</span><span class="sxs-lookup"><span data-stu-id="57d93-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="57d93-235">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="57d93-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="57d93-237">В разделе **Добавление записи зоны**выберите **запись TXT** в списке, а затем выберите **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="57d93-239">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="57d93-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="57d93-240">Перед и после записи в поле TXT необходимо использовать кавычки.</span><span class="sxs-lookup"><span data-stu-id="57d93-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="57d93-241">**Имя**</span><span class="sxs-lookup"><span data-stu-id="57d93-241">**Name**</span></span>|<span data-ttu-id="57d93-242">**Тип**</span><span class="sxs-lookup"><span data-stu-id="57d93-242">**Type**</span></span>|<span data-ttu-id="57d93-243">**TTL (Срок жизни)**</span><span class="sxs-lookup"><span data-stu-id="57d93-243">**TTL**</span></span>|<span data-ttu-id="57d93-244">**Данные TXT (Target)**</span><span class="sxs-lookup"><span data-stu-id="57d93-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57d93-245">(Оставьте пустым)</span><span class="sxs-lookup"><span data-stu-id="57d93-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="57d93-246">TXT</span><span class="sxs-lookup"><span data-stu-id="57d93-246">TXT</span></span>  <br/> |<span data-ttu-id="57d93-247">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-248">"v = spf1 включает:SPF. Protection. Outlook. com-ALL"</span><span class="sxs-lookup"><span data-stu-id="57d93-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="57d93-249">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="57d93-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF Ткствалуес](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="57d93-251">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="57d93-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="57d93-253">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="57d93-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="57d93-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="57d93-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="57d93-p112">Чтобы приступить к работе, откройте страницу со своими доменами на веб-сайте Netregistry по [этой ссылке](https://theconsole.netregistry.com.au/). Вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57d93-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="57d93-258">Рядом с доменом, которым вы хотите управлять, выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="57d93-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="57d93-260">Выберите пункт **Zone Manager** (Диспетчер зон).</span><span class="sxs-lookup"><span data-stu-id="57d93-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="57d93-262">В разделе **Добавление записи зоны**выберите **запись SRV** из списка и нажмите кнопку **создать новую запись**.</span><span class="sxs-lookup"><span data-stu-id="57d93-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="57d93-264">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="57d93-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57d93-265">Поле Name — это сочетание службы (например, _sip) и протокола (например, _tls).</span><span class="sxs-lookup"><span data-stu-id="57d93-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="57d93-266">**Тип**</span><span class="sxs-lookup"><span data-stu-id="57d93-266">**Type**</span></span>|<span data-ttu-id="57d93-267">**Name (Имя)**</span><span class="sxs-lookup"><span data-stu-id="57d93-267">**Name**</span></span>|<span data-ttu-id="57d93-268">**TTL (SEC) (Срок жизни в секундах)**</span><span class="sxs-lookup"><span data-stu-id="57d93-268">**TTL (SEC)**</span></span>|<span data-ttu-id="57d93-269">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="57d93-269">**Priority**</span></span>|<span data-ttu-id="57d93-270">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="57d93-270">**Weight**</span></span>|<span data-ttu-id="57d93-271">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="57d93-271">**Port**</span></span>|<span data-ttu-id="57d93-272">**Target (Назначение)**</span><span class="sxs-lookup"><span data-stu-id="57d93-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57d93-273">SRV (служба)</span><span class="sxs-lookup"><span data-stu-id="57d93-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="57d93-274">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="57d93-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="57d93-275">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-276">100</span><span class="sxs-lookup"><span data-stu-id="57d93-276">100</span></span>  <br/> |<span data-ttu-id="57d93-277">1,1</span><span class="sxs-lookup"><span data-stu-id="57d93-277">1</span></span>  <br/> |<span data-ttu-id="57d93-278">443</span><span class="sxs-lookup"><span data-stu-id="57d93-278">443</span></span>  <br/> |<span data-ttu-id="57d93-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57d93-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57d93-280">SRV (служба)</span><span class="sxs-lookup"><span data-stu-id="57d93-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="57d93-281">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="57d93-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="57d93-282">3600 (секунд)</span><span class="sxs-lookup"><span data-stu-id="57d93-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57d93-283">100</span><span class="sxs-lookup"><span data-stu-id="57d93-283">100</span></span>  <br/> |<span data-ttu-id="57d93-284">1,1</span><span class="sxs-lookup"><span data-stu-id="57d93-284">1</span></span>  <br/> |<span data-ttu-id="57d93-285">5061</span><span class="sxs-lookup"><span data-stu-id="57d93-285">5061</span></span>  <br/> |<span data-ttu-id="57d93-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57d93-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="57d93-288">Выберите команду **Add Record** (Добавить запись).</span><span class="sxs-lookup"><span data-stu-id="57d93-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="57d93-290">Повторите эти действия для другой записи SRV.</span><span class="sxs-lookup"><span data-stu-id="57d93-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="57d93-291">В поля для второй записи введите (или скопируйте и вставьте) значения из второй строки приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="57d93-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="57d93-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57d93-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

