---
title: Создание записей DNS на сайте eNomCentral для Майкрософт
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Узнайте, как проверить домен и настроить записи DNS для электронной почты, Skype для бизнеса Online и других служб по адресу eNomCentral для Майкрософт.
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780401"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="1fdcc-103">Создание записей DNS на сайте eNomCentral для Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1fdcc-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="1fdcc-104">**[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1fdcc-105">Если ваш поставщик услуг размещения DNS  eNomCentral, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1fdcc-106">Когда вы добавите эти записи на сайте eNomCentral, ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="1fdcc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1fdcc-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1fdcc-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1fdcc-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="1fdcc-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1fdcc-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1fdcc-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1fdcc-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="1fdcc-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fdcc-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="1fdcc-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="1fdcc-116">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="1fdcc-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-117">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="1fdcc-118">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-118">You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="1fdcc-120">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="1fdcc-122">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — Verify – 1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="1fdcc-124">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="1fdcc-125">В раскрывающемся списке выберите значение **тип записи** .</span><span class="sxs-lookup"><span data-stu-id="1fdcc-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="1fdcc-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-126">**Host Name**</span></span> <br/> |<span data-ttu-id="1fdcc-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-127">**Record Type**</span></span> <br/> |<span data-ttu-id="1fdcc-128">**Address** (Адрес)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="1fdcc-129">TXT</span><span class="sxs-lookup"><span data-stu-id="1fdcc-129">TXT</span></span>  <br/> |<span data-ttu-id="1fdcc-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1fdcc-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1fdcc-131">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-131">**Note:** This is an example.</span></span> <span data-ttu-id="1fdcc-132">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1fdcc-133">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="1fdcc-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom Central — BP — Verify – 1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="1fdcc-135">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-135">Select **save**.</span></span>
    
    ![eNom Central — BP — Verify – 1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="1fdcc-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1fdcc-138">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="1fdcc-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1fdcc-140">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1fdcc-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1fdcc-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1fdcc-143">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1fdcc-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1fdcc-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1fdcc-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1fdcc-147">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1fdcc-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1fdcc-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1fdcc-149">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="1fdcc-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-150">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="1fdcc-151">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-151">You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="1fdcc-153">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="1fdcc-155">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Email Settings** (Параметры электронной почты).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom Central — BP — configure – 1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="1fdcc-157">В раскрывающемся списке **Service Selection** (Выбор службы) выберите пункт **User (MX)** (Пользователь (MX).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom Central — BP — configure – 1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="1fdcc-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1fdcc-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-160">**Host Name**</span></span>|<span data-ttu-id="1fdcc-161">**Address**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-161">**Address**</span></span>|<span data-ttu-id="1fdcc-162">**Pref (Предпочтение)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="1fdcc-163">*\<domain-key\>*. mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1fdcc-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1fdcc-165">**Примечание:** Получение *\<domain-key\>* учетной записи Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1fdcc-166">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="1fdcc-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1fdcc-167">10 </span><span class="sxs-lookup"><span data-stu-id="1fdcc-167">10</span></span>  <br/> <span data-ttu-id="1fdcc-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="1fdcc-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
       
   ![eNom Central — BP — configure – 2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="1fdcc-170">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-170">Select **save**.</span></span>
    
    ![eNom Central — BP — configure – 2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="1fdcc-172">Если в списке указаны другие существующие записи MX, установите для них флажки, чтобы выбрать их.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom Central — BP — configure – 2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="1fdcc-174">Выберите вариант **Удалить проверено**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-174">Select **delete checked**.</span></span>
    
    ![eNom Central — BP — configure – 2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1fdcc-176">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1fdcc-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="1fdcc-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1fdcc-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1fdcc-178">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="1fdcc-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-179">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="1fdcc-180">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-180">You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="1fdcc-182">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="1fdcc-184">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — configure – 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="1fdcc-186">Выберите пункт **создать строку**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-186">Select **new row**.</span></span>
    
    ![eNom Central — BP — configure – 3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="1fdcc-188">В поля для шести новых записей введите (или скопируйте и вставьте) следующие значения.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="1fdcc-189">В раскрывающемся списке выберите значение **тип записи** .</span><span class="sxs-lookup"><span data-stu-id="1fdcc-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="1fdcc-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-190">**Host Name**</span></span>|<span data-ttu-id="1fdcc-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-191">**Record Type**</span></span>|<span data-ttu-id="1fdcc-192">**Address (Адрес)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="1fdcc-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1fdcc-193">autodiscover</span></span>  <br/> |<span data-ttu-id="1fdcc-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1fdcc-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1fdcc-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1fdcc-197">sip</span><span class="sxs-lookup"><span data-stu-id="1fdcc-197">sip</span></span>  <br/> |<span data-ttu-id="1fdcc-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1fdcc-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1fdcc-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1fdcc-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1fdcc-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1fdcc-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1fdcc-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1fdcc-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1fdcc-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1fdcc-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1fdcc-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1fdcc-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1fdcc-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1fdcc-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1fdcc-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1fdcc-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="1fdcc-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1fdcc-212">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="1fdcc-213">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-213">Select **save**.</span></span>
    
    ![eNom Central — BP — configure – 3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1fdcc-215">Добавьте запись TXT для SPF, чтобы предотвратить рассылку спама</span><span class="sxs-lookup"><span data-stu-id="1fdcc-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1fdcc-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1fdcc-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fdcc-217">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1fdcc-218">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1fdcc-219">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1fdcc-220">Вместо этого добавьте необходимые значения Майкрософт в текущую запись, чтобы иметь *одну* запись SPF, включающую оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="1fdcc-221">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-221">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="1fdcc-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-222">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="1fdcc-223">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-223">You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="1fdcc-225">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="1fdcc-227">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — configure – 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="1fdcc-229">В поля для новой записи введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="1fdcc-230">В раскрывающемся списке выберите значение **тип записи** .</span><span class="sxs-lookup"><span data-stu-id="1fdcc-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="1fdcc-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-231">**Host Name**</span></span>|<span data-ttu-id="1fdcc-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-232">**Record Type**</span></span>|<span data-ttu-id="1fdcc-233">**Address** (Адрес)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="1fdcc-234">TXT</span><span class="sxs-lookup"><span data-stu-id="1fdcc-234">TXT</span></span>  <br/> |<span data-ttu-id="1fdcc-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1fdcc-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="1fdcc-236">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="1fdcc-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom Central — BP — configure – 4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="1fdcc-238">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-238">Select **save**.</span></span>
    
    ![eNom Central — BP — configure – 4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1fdcc-240">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1fdcc-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1fdcc-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1fdcc-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1fdcc-242">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-242">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>
  
1. <span data-ttu-id="1fdcc-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-243">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered).</span></span> <span data-ttu-id="1fdcc-244">You'll be prompted to login.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-244">You'll be prompted to login.</span></span>
    
    ![eNom Central — BP — configure – 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="1fdcc-246">В разделе **My Domains (мои домены**) выберите имя домена, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom Central — BP — configure – 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="1fdcc-248">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom Central — BP — configure – 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="1fdcc-250">Справа от **новой строки**выберите **Добавить запись SRV или SPF**.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom Central — BP — configure – 5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="1fdcc-252">В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1fdcc-253">**Service (Служба)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-253">**Service**</span></span>|<span data-ttu-id="1fdcc-254">**Protocol (Протокол)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-254">**Protocol**</span></span>|<span data-ttu-id="1fdcc-255">**Priority** (Приоритет)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-255">**Priority**</span></span>|<span data-ttu-id="1fdcc-256">**Weight** (Вес)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-256">**Weight**</span></span>|<span data-ttu-id="1fdcc-257">**Port** (Порт)</span><span class="sxs-lookup"><span data-stu-id="1fdcc-257">**Port**</span></span>|<span data-ttu-id="1fdcc-258">**Target          (Hostname) (Узел назначения)**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1fdcc-259">_sip</span><span class="sxs-lookup"><span data-stu-id="1fdcc-259">_sip</span></span>  <br/> |<span data-ttu-id="1fdcc-260">_tls</span><span class="sxs-lookup"><span data-stu-id="1fdcc-260">_tls</span></span>  <br/> |<span data-ttu-id="1fdcc-261">100</span><span class="sxs-lookup"><span data-stu-id="1fdcc-261">100</span></span>  <br/> |<span data-ttu-id="1fdcc-262">1 </span><span class="sxs-lookup"><span data-stu-id="1fdcc-262">1</span></span>  <br/> |<span data-ttu-id="1fdcc-263">443</span><span class="sxs-lookup"><span data-stu-id="1fdcc-263">443</span></span>  <br/> |<span data-ttu-id="1fdcc-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1fdcc-265">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1fdcc-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1fdcc-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="1fdcc-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="1fdcc-267">_tcp</span></span>  <br/> |<span data-ttu-id="1fdcc-268">100</span><span class="sxs-lookup"><span data-stu-id="1fdcc-268">100</span></span>  <br/> |<span data-ttu-id="1fdcc-269">1 </span><span class="sxs-lookup"><span data-stu-id="1fdcc-269">1</span></span>  <br/> |<span data-ttu-id="1fdcc-270">5061</span><span class="sxs-lookup"><span data-stu-id="1fdcc-270">5061</span></span>  <br/> |<span data-ttu-id="1fdcc-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="1fdcc-272">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom Central — BP — configure – 5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="1fdcc-274">Нажмите кнопку **сохранить**</span><span class="sxs-lookup"><span data-stu-id="1fdcc-274">Select **save**</span></span>
    
    ![eNom Central — BP — configure – 5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="1fdcc-276">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-276">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="1fdcc-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="1fdcc-277">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="1fdcc-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1fdcc-278">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

