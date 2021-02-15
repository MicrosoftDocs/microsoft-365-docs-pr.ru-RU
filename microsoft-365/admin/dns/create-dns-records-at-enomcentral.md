---
title: Создание записей DNS для Майкрософт на сайте eNomCentral
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at eNomCentral for Microsoft.
ms.openlocfilehash: e6e05b987a893da582ea7fb062eafe421861b970
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658115"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="e44e8-103">Создание записей DNS для Майкрософт на сайте eNomCentral</span><span class="sxs-lookup"><span data-stu-id="e44e8-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="e44e8-104">**[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="e44e8-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="e44e8-105">Если ваш поставщик услуг размещения DNS  eNomCentral, выполните действия, описанные в этой статье, чтобы подтвердить владение доменом и настроить записи DNS для электронной почты, Skype для бизнеса online и других служб.</span><span class="sxs-lookup"><span data-stu-id="e44e8-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="e44e8-106">После добавления этих записей на сайте eNomCentral ваш домен будет настроен для работы со службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e44e8-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="e44e8-p101">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e44e8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e44e8-110">Добавление записи TXT для проверки</span><span class="sxs-lookup"><span data-stu-id="e44e8-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e44e8-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e44e8-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e44e8-p102">Прежде чем вы сможете использовать свой домен при работе с продуктами корпорации Майкрософт, мы должны убедиться в том, что вы являетесь его владельцем. Если вы войдете в свою учетную запись на сайте регистратора доменных имен и создадите запись DNS, для корпорации Майкрософт это послужит подтверждением того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="e44e8-p103">Эта запись используется исключительно для проверки принадлежности домена. При желании вы сможете удалить ее позже.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="e44e8-116">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="e44e8-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="e44e8-p104">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="e44e8-120">В **моих доменах** выберите имя домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e44e8-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="e44e8-122">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="e44e8-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="e44e8-124">В поля для новой записи введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e44e8-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="e44e8-125">В **выпадаемом списке** выберите значение Record Type (Тип записи).</span><span class="sxs-lookup"><span data-stu-id="e44e8-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="e44e8-126">Имя узла</span><span class="sxs-lookup"><span data-stu-id="e44e8-126">Host Name</span></span>|<span data-ttu-id="e44e8-127">Record Type</span><span class="sxs-lookup"><span data-stu-id="e44e8-127">Record Type</span></span>|<span data-ttu-id="e44e8-128">Address</span><span class="sxs-lookup"><span data-stu-id="e44e8-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="e44e8-129">TXT</span><span class="sxs-lookup"><span data-stu-id="e44e8-129">TXT</span></span>|<span data-ttu-id="e44e8-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e44e8-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e44e8-131">**Примечание.** Это пример.</span><span class="sxs-lookup"><span data-stu-id="e44e8-131">**Note:** This is an example.</span></span> <span data-ttu-id="e44e8-132">Используйте здесь свое конкретное значение **Назначение или адрес "Указывает на"** из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e44e8-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e44e8-133">Как его найти?</span><span class="sxs-lookup"><span data-stu-id="e44e8-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="e44e8-135">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e44e8-135">Select **save**.</span></span>

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="e44e8-137">Подождите несколько минут, пока созданная запись не будет обновлена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e44e8-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="e44e8-138">Теперь, когда запись добавлена на сайте регистратора доменных имен, вернитесь в Microsoft 365 и подайте запрос на ее поиск.</span><span class="sxs-lookup"><span data-stu-id="e44e8-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="e44e8-139">Когда продукт корпорации Майкрософт обнаружит правильную запись TXT, ваш домен будет подтвержден.</span><span class="sxs-lookup"><span data-stu-id="e44e8-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="e44e8-140">В центре администрирования Майкрософт перейдите на страницу **Настройка** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены</a>.</span><span class="sxs-lookup"><span data-stu-id="e44e8-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="e44e8-141">На странице **Domains** (Домены) выберите домен, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="e44e8-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="e44e8-142">На странице **Setup** (Настройка) выберите **Start setup** (Начать настройку).</span><span class="sxs-lookup"><span data-stu-id="e44e8-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="e44e8-143">На странице **Проверка домена** выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="e44e8-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="e44e8-p106">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e44e8-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e44e8-147">Добавьте запись MX, чтобы сообщения электронной почты для вашего домена доставлялись в продукты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e44e8-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e44e8-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e44e8-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="e44e8-149">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="e44e8-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="e44e8-p107">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="e44e8-153">В **моих доменах** выберите имя домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e44e8-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="e44e8-155">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Email Settings** (Параметры электронной почты).</span><span class="sxs-lookup"><span data-stu-id="e44e8-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="e44e8-157">В раскрывающемся списке **Service Selection** (Выбор службы) выберите пункт **User (MX)** (Пользователь (MX).</span><span class="sxs-lookup"><span data-stu-id="e44e8-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="e44e8-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e44e8-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="e44e8-160">Имя узла</span><span class="sxs-lookup"><span data-stu-id="e44e8-160">Host Name</span></span>|<span data-ttu-id="e44e8-161">Address</span><span class="sxs-lookup"><span data-stu-id="e44e8-161">Address</span></span>|<span data-ttu-id="e44e8-162">Pref (Предпочтение)</span><span class="sxs-lookup"><span data-stu-id="e44e8-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="e44e8-163">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e44e8-164">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e44e8-165">**Примечание.** Получите свою  *\<domain-key\>*  учетную запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e44e8-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="e44e8-166">Где это находится?</span><span class="sxs-lookup"><span data-stu-id="e44e8-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="e44e8-167">10 </span><span class="sxs-lookup"><span data-stu-id="e44e8-167">10</span></span>  <br/> <span data-ttu-id="e44e8-168">Дополнительные сведения о приоритете см. в статье [Приоритет записей MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).   </span><span class="sxs-lookup"><span data-stu-id="e44e8-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span>|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="e44e8-170">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e44e8-170">Select **save**.</span></span>

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="e44e8-172">Если в списке указаны другие существующие записи MX, установите для них флажки, чтобы выбрать их.</span><span class="sxs-lookup"><span data-stu-id="e44e8-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="e44e8-174">Select **delete checked**.</span><span class="sxs-lookup"><span data-stu-id="e44e8-174">Select **delete checked**.</span></span>

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e44e8-176">Добавление записей CNAME, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e44e8-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e44e8-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e44e8-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="e44e8-178">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="e44e8-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="e44e8-p109">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="e44e8-182">В **моих доменах** выберите имя домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e44e8-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="e44e8-184">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="e44e8-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="e44e8-186">Выберите **новую строку.**</span><span class="sxs-lookup"><span data-stu-id="e44e8-186">Select **new row**.</span></span>

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="e44e8-188">В поля для шести новых записей введите (или скопируйте и вставьте) следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e44e8-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="e44e8-189">В **выпадаемом списке** выберите значение Record Type (Тип записи).</span><span class="sxs-lookup"><span data-stu-id="e44e8-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="e44e8-190">Имя узла</span><span class="sxs-lookup"><span data-stu-id="e44e8-190">Host Name</span></span>|<span data-ttu-id="e44e8-191">Record Type</span><span class="sxs-lookup"><span data-stu-id="e44e8-191">Record Type</span></span>|<span data-ttu-id="e44e8-192">Address</span><span class="sxs-lookup"><span data-stu-id="e44e8-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="e44e8-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e44e8-193">autodiscover</span></span>|<span data-ttu-id="e44e8-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="e44e8-194">CNAME (Alias)</span></span>|<span data-ttu-id="e44e8-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e44e8-196">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="e44e8-197">sip</span><span class="sxs-lookup"><span data-stu-id="e44e8-197">sip</span></span>|<span data-ttu-id="e44e8-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="e44e8-198">CNAME (Alias)</span></span>|<span data-ttu-id="e44e8-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e44e8-200">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="e44e8-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e44e8-201">lyncdiscover</span></span>|<span data-ttu-id="e44e8-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="e44e8-202">CNAME (Alias)</span></span>|<span data-ttu-id="e44e8-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e44e8-204">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="e44e8-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e44e8-205">enterpriseregistration</span></span>|<span data-ttu-id="e44e8-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="e44e8-206">CNAME (Alias)</span></span>|<span data-ttu-id="e44e8-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e44e8-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e44e8-208">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="e44e8-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e44e8-209">enterpriseenrollment</span></span>|<span data-ttu-id="e44e8-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="e44e8-210">CNAME (Alias)</span></span>|<span data-ttu-id="e44e8-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e44e8-212">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="e44e8-214">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e44e8-214">Select **save**.</span></span>

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e44e8-216">Добавление записи TXT для SPF, предотвращающей рассылку спама</span><span class="sxs-lookup"><span data-stu-id="e44e8-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e44e8-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e44e8-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e44e8-218">Для записи инфраструктуры политики отправителей (SPF) для домена можно указать только одну запись TXT.</span><span class="sxs-lookup"><span data-stu-id="e44e8-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e44e8-219">Если у вашего домена больше одной записи SPF, это приведет к сбоям в работе почты и ошибкам классификации входящих писем и спама.</span><span class="sxs-lookup"><span data-stu-id="e44e8-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e44e8-220">Если вы уже указали запись SPF для домена, не создавайте еще одну для продуктов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e44e8-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e44e8-221">Вместо этого добавьте необходимые значения Майкрософт в текущую  запись, чтобы иметь одну запись SPF, которая включает оба набора значений.</span><span class="sxs-lookup"><span data-stu-id="e44e8-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="e44e8-222">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="e44e8-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="e44e8-p111">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="e44e8-226">В **моих доменах** выберите имя домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e44e8-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="e44e8-228">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="e44e8-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="e44e8-230">В поля для новой записи введите (или скопируйте и вставьте) значения из приведенной ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="e44e8-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="e44e8-231">В **выпадаемом списке** выберите значение Record Type (Тип записи).</span><span class="sxs-lookup"><span data-stu-id="e44e8-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="e44e8-232">Имя узла</span><span class="sxs-lookup"><span data-stu-id="e44e8-232">Host Name</span></span>|<span data-ttu-id="e44e8-233">Record Type</span><span class="sxs-lookup"><span data-stu-id="e44e8-233">Record Type</span></span>|<span data-ttu-id="e44e8-234">Address</span><span class="sxs-lookup"><span data-stu-id="e44e8-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="e44e8-235">TXT</span><span class="sxs-lookup"><span data-stu-id="e44e8-235">TXT</span></span>|<span data-ttu-id="e44e8-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e44e8-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="e44e8-237">**Примечание.** Рекомендуется скопировать и вставить эту запись, чтобы сохранить все пробелы.    </span><span class="sxs-lookup"><span data-stu-id="e44e8-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="e44e8-239">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e44e8-239">Select **save**.</span></span>

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e44e8-241">Добавление двух записей SRV, необходимых для продуктов корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e44e8-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e44e8-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e44e8-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="e44e8-243">Воспользуйтесь приведенными ниже инструкциями или [посмотрите видеоролик (начиная с 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="e44e8-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="e44e8-p112">Чтобы приступить к работе, перейдите на свою страницу доменов на сайте eNom Central по [этой ссылке](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Сперва вам потребуется выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="e44e8-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="e44e8-247">В **моих доменах** выберите имя домена, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="e44e8-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="e44e8-249">В раскрывающемся списке **Manage Domain** (Управление доменом) выберите пункт **Host Records** (Записи узлов).</span><span class="sxs-lookup"><span data-stu-id="e44e8-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="e44e8-251">Справа от новой **строки выберите**"Добавить запись SRV или **SPF".**</span><span class="sxs-lookup"><span data-stu-id="e44e8-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="e44e8-253">В поля для двух новых записей введите (или скопируйте и вставьте) значения из таблицы ниже.</span><span class="sxs-lookup"><span data-stu-id="e44e8-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="e44e8-254">Служба</span><span class="sxs-lookup"><span data-stu-id="e44e8-254">Service</span></span>|<span data-ttu-id="e44e8-255">Протокол</span><span class="sxs-lookup"><span data-stu-id="e44e8-255">Protocol</span></span>|<span data-ttu-id="e44e8-256">Priority</span><span class="sxs-lookup"><span data-stu-id="e44e8-256">Priority</span></span>|<span data-ttu-id="e44e8-257">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="e44e8-257">Weight</span></span>|<span data-ttu-id="e44e8-258">Порт</span><span class="sxs-lookup"><span data-stu-id="e44e8-258">Port</span></span>|<span data-ttu-id="e44e8-259">Target (Hostname)</span><span class="sxs-lookup"><span data-stu-id="e44e8-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="e44e8-260">_sip</span><span class="sxs-lookup"><span data-stu-id="e44e8-260">_sip</span></span>|<span data-ttu-id="e44e8-261">_tls</span><span class="sxs-lookup"><span data-stu-id="e44e8-261">_tls</span></span>|<span data-ttu-id="e44e8-262">100</span><span class="sxs-lookup"><span data-stu-id="e44e8-262">100</span></span>|<span data-ttu-id="e44e8-263">1 </span><span class="sxs-lookup"><span data-stu-id="e44e8-263">1</span></span>|<span data-ttu-id="e44e8-264">443</span><span class="sxs-lookup"><span data-stu-id="e44e8-264">443</span></span>|<span data-ttu-id="e44e8-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e44e8-266">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="e44e8-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e44e8-267">_sipfederationtls</span></span>|<span data-ttu-id="e44e8-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="e44e8-268">_tcp</span></span>|<span data-ttu-id="e44e8-269">100</span><span class="sxs-lookup"><span data-stu-id="e44e8-269">100</span></span>|<span data-ttu-id="e44e8-270">1 </span><span class="sxs-lookup"><span data-stu-id="e44e8-270">1</span></span>|<span data-ttu-id="e44e8-271">5061</span><span class="sxs-lookup"><span data-stu-id="e44e8-271">5061</span></span>|<span data-ttu-id="e44e8-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e44e8-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="e44e8-273">**Это значение ДОЛЖНО оканчиваться точкой (.).**</span><span class="sxs-lookup"><span data-stu-id="e44e8-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="e44e8-275">Выберите **"Сохранить"**</span><span class="sxs-lookup"><span data-stu-id="e44e8-275">Select **save**</span></span>

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="e44e8-p113">Обычно на вступление изменений DNS в силу требуется около 15 минут. Однако иногда распространение внесенного изменения в системе DNS по всему Интернету занимает больше времени. Если после добавления записей DNS возникла проблема с потоком обработки почты или другие неполадки, см. статью [Устранение неполадок после смены имени домена или записей DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e44e8-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
