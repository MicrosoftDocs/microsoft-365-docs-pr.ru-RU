---
title: Отправки администратором
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать портал отправки в центре безопасности & соответствия требованиям для отправки подозрительных сообщений электронной почты, подозрительных сообщений фишинга, спама и других потенциально опасных сообщений, URL-адресов и файлов в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: 0c01afff2e9e5a656099192f3867bb3a6f1cee23
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568594"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="97ff3-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="97ff3-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="97ff3-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал отправки в центре безопасности & соответствия требованиям для отправки электронных сообщений, URL-адресов и вложений в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="97ff3-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="97ff3-105">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="97ff3-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="97ff3-106">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="97ff3-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="97ff3-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="97ff3-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="97ff3-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="97ff3-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="97ff3-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="97ff3-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="97ff3-110">Чтобы перейти непосредственно на страницу **отправки** , используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="97ff3-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="97ff3-111">Чтобы передать сообщения и файлы в корпорацию Майкрософт, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="97ff3-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="97ff3-112">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="97ff3-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="97ff3-113">**Управление организацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="97ff3-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="97ff3-114">Обратите внимание, что членство в этой группе ролей необходимо для [просмотра отправки пользователей в пользовательский почтовый ящик](#view-user-submissions-to-the-custom-mailbox) , как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="97ff3-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="97ff3-115">Для получения дополнительных сведений о том, как пользователи могут отсылать сообщения и файлы в корпорацию Майкрософт, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="97ff3-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="97ff3-116">Сообщить о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="97ff3-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="97ff3-117">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** \> **Submissions**", убедитесь, что вы находитесь на вкладке " **отправленные администратором** ", а затем нажмите кнопку **создать отправку**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="97ff3-118">Используйте всплывающее всплывающее окно **отправки** , которое появляется для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="97ff3-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="97ff3-119">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="97ff3-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="97ff3-120">В разделе **тип объекта** выберите **Электронная почта**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="97ff3-121">В разделе **формат отправки** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="97ff3-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="97ff3-122">**Идентификатор сетевого сообщения**: это значение GUID, которое доступно в заголовке **x-MS-Exchange-Organization-Network-Message-ID** в сообщении или в заголовке **X-MS-Office365-Filter-Correlation-ID** в сообщениях, помещенных в карантин.</span><span class="sxs-lookup"><span data-stu-id="97ff3-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="97ff3-123">**Файл**: нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="97ff3-124">В открывшемся диалоговом окне найдите и выберите файл. EML или. MSG, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="97ff3-125">Администраторы с защитником для Office 365 (план 1) или 1 (план 2) могут отсылать сообщения от старых дней до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="97ff3-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="97ff3-126">Другие администраторы смогут перейти только на 7 дней.</span><span class="sxs-lookup"><span data-stu-id="97ff3-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="97ff3-127">В разделе **получатели** укажите одного или нескольких получателей, для которых необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="97ff3-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="97ff3-128">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="97ff3-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="97ff3-129">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="97ff3-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="97ff3-130">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="97ff3-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="97ff3-131">**Должны быть заблокированы**: выберите **спам**, **Фишинг** или **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="97ff3-132">Если вы не уверены, используйте свои лучшие решения.</span><span class="sxs-lookup"><span data-stu-id="97ff3-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="97ff3-133">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="97ff3-133">When you're finished, click the **Submit** button.</span></span>

![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="97ff3-135">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="97ff3-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="97ff3-136">В разделе **тип объекта** выберите **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="97ff3-137">В появившемся поле введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="97ff3-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="97ff3-138">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="97ff3-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="97ff3-139">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="97ff3-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="97ff3-140">**Должны быть заблокированы**: выберите **Фишинг** или **вредоносную** программу.</span><span class="sxs-lookup"><span data-stu-id="97ff3-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="97ff3-141">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="97ff3-141">When you're finished, click the **Submit** button.</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="97ff3-143">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="97ff3-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="97ff3-144">В разделе **тип объекта** выберите **вложение**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="97ff3-145">Нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-145">Click **Choose File**.</span></span> <span data-ttu-id="97ff3-146">В открывшемся диалоговом окне найдите и выберите файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="97ff3-147">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="97ff3-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="97ff3-148">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="97ff3-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="97ff3-149">**Должны быть заблокированы**: **единственным** выбором и автоматически выбрано значение...</span><span class="sxs-lookup"><span data-stu-id="97ff3-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="97ff3-150">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="97ff3-150">When you're finished, click the **Submit** button.</span></span>

![Пример отправки вложений](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="97ff3-152">Просмотр отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="97ff3-152">View admin submissions</span></span>

<span data-ttu-id="97ff3-153">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** \> **Submissions**", убедитесь, что вы находитесь на вкладке " **отправленные администратором** ", а затем нажмите кнопку **создать отправку**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="97ff3-154">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **идентификатору отправки** (значение GUID, назначенное каждой отправке), введя значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="97ff3-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="97ff3-155">Update</span><span class="sxs-lookup"><span data-stu-id="97ff3-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="97ff3-156">Чтобы изменить условия фильтра, нажмите кнопку " **идентификатор отправки** " и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="97ff3-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="97ff3-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="97ff3-157">**Sender**</span></span>
- <span data-ttu-id="97ff3-158">**Тема/URL-адрес/имя файла**</span><span class="sxs-lookup"><span data-stu-id="97ff3-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="97ff3-159">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="97ff3-159">**Submitted by**</span></span>
- <span data-ttu-id="97ff3-160">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-160">**Submission type**</span></span>
- <span data-ttu-id="97ff3-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="97ff3-161">**Status**</span></span>

![Параметры фильтра для отправки администратором](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="97ff3-163">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="97ff3-164">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="97ff3-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="97ff3-165">Под диаграммой расположены три вкладки: **Электронная почта** (по умолчанию), **URL-адрес** и **вложение**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="97ff3-166">Просмотр отправляемых по электронной почте сообщений администратора</span><span class="sxs-lookup"><span data-stu-id="97ff3-166">View admin email submissions</span></span>

<span data-ttu-id="97ff3-167">Перейдите на вкладку **Электронная почта** .</span><span class="sxs-lookup"><span data-stu-id="97ff3-167">Click the **Email** tab.</span></span>

<span data-ttu-id="97ff3-168">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="97ff3-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="97ff3-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="97ff3-169">**Date**</span></span>
- <span data-ttu-id="97ff3-170">**Идентификатор отправки**: значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="97ff3-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="97ff3-171">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-172">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="97ff3-173">**Sender**</span></span>
- <span data-ttu-id="97ff3-174">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-175">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-175">**Submission type**</span></span>
- <span data-ttu-id="97ff3-176">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-176">**Delivery reason**</span></span>
- <span data-ttu-id="97ff3-177">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="97ff3-178"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="97ff3-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="97ff3-179">Сведения о повторном сканировании отправки администратором</span><span class="sxs-lookup"><span data-stu-id="97ff3-179">Admin submission rescan details</span></span>

<span data-ttu-id="97ff3-180">Сообщения, отправленные в отправки администратором, повторно сканируются, а результаты отображаются в всплывающем меню сведений:</span><span class="sxs-lookup"><span data-stu-id="97ff3-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="97ff3-181">Если во время доставки произошел сбой проверки подлинности электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="97ff3-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="97ff3-182">Сведения обо всех найденных политиках, которые могут повлиять на вредоносности сообщение или переопределить его.</span><span class="sxs-lookup"><span data-stu-id="97ff3-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="97ff3-183">Current детонации results, чтобы узнать, являются ли URL-адреса или файлы, которые содержатся в сообщении, нежелательными.</span><span class="sxs-lookup"><span data-stu-id="97ff3-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="97ff3-184">Отзывы и предложения.</span><span class="sxs-lookup"><span data-stu-id="97ff3-184">Feedback from graders.</span></span>

<span data-ttu-id="97ff3-185">Если обнаружено переопределение, повторное сканирование должно завершиться через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="97ff3-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="97ff3-186">Если при проверке подлинности электронной почты или доставке не было затронуты переопределение, обратная связь от более неисправностей может длиться до суток.</span><span class="sxs-lookup"><span data-stu-id="97ff3-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="97ff3-187">Просмотр отправок URL-адреса администратора</span><span class="sxs-lookup"><span data-stu-id="97ff3-187">View admin URL submissions</span></span>

<span data-ttu-id="97ff3-188">Перейдите на вкладку **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="97ff3-188">Click the **URL** tab.</span></span>

<span data-ttu-id="97ff3-189">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="97ff3-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="97ff3-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="97ff3-190">**Date**</span></span>
- <span data-ttu-id="97ff3-191">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-191">**Submission ID**</span></span>
- <span data-ttu-id="97ff3-192">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-194">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-194">**Submission type**</span></span>
- <span data-ttu-id="97ff3-195">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="97ff3-196"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="97ff3-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="97ff3-197">Просмотр отправки вложений администратора</span><span class="sxs-lookup"><span data-stu-id="97ff3-197">View admin attachment submissions</span></span>

<span data-ttu-id="97ff3-198">Перейдите на вкладку **вложения** .</span><span class="sxs-lookup"><span data-stu-id="97ff3-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="97ff3-199">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="97ff3-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="97ff3-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="97ff3-200">**Date**</span></span>
- <span data-ttu-id="97ff3-201">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-201">**Submission ID**</span></span>
- <span data-ttu-id="97ff3-202">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-203">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-204">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-204">**Submission type**</span></span>
- <span data-ttu-id="97ff3-205">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="97ff3-206"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="97ff3-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="97ff3-207">Просмотр отправленных пользователем данных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="97ff3-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="97ff3-208">Если вы развернули [надстройку "сообщение отчета](enable-the-report-message-add-in.md)" или используете [встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), вы можете увидеть, какие пользователи будут создавать отчеты на вкладке " **Отправленные пользователем** ".</span><span class="sxs-lookup"><span data-stu-id="97ff3-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="97ff3-209">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** " \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="97ff3-210">Выберите вкладку **отправки пользователей** и нажмите кнопку **создать отправку**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="97ff3-211">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="97ff3-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="97ff3-212">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="97ff3-212">**Submitted on**</span></span>
- <span data-ttu-id="97ff3-213">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-214">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="97ff3-215">**Sender**</span></span>
- <span data-ttu-id="97ff3-216">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-217">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-217">**Submission type**</span></span>

<span data-ttu-id="97ff3-218"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="97ff3-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="97ff3-219">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **отправителю** , указав значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="97ff3-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="97ff3-220">Update</span><span class="sxs-lookup"><span data-stu-id="97ff3-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="97ff3-221">Чтобы изменить условия фильтра, нажмите кнопку **отправитель** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="97ff3-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="97ff3-222">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="97ff3-222">**Sender domain**</span></span>
- <span data-ttu-id="97ff3-223">**Subject**</span><span class="sxs-lookup"><span data-stu-id="97ff3-223">**Subject**</span></span>
- <span data-ttu-id="97ff3-224">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="97ff3-224">**Submitted by**</span></span>
- <span data-ttu-id="97ff3-225">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-225">**Submission type**</span></span>
- <span data-ttu-id="97ff3-226">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="97ff3-226">**Sender IP**</span></span>

![Параметры фильтра для отправки пользователя](../../media/user-submissions-filter-options.png)

<span data-ttu-id="97ff3-228">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="97ff3-229">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="97ff3-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="97ff3-230">Просмотр отправленных пользователем данных в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="97ff3-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="97ff3-231">**Если** вы [настроили настраиваемый почтовый ящик](user-submission.md) для получения сообщений, отправленных пользователями, вы можете просматривать и отправлять сообщения, которые были доставлены в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="97ff3-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="97ff3-232">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** " \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="97ff3-233">Перейдите на вкладку **настраиваемый почтовый ящик** .</span><span class="sxs-lookup"><span data-stu-id="97ff3-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="97ff3-234">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="97ff3-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="97ff3-235">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="97ff3-235">**Submitted on**</span></span>
- <span data-ttu-id="97ff3-236">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-237">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="97ff3-238">**Sender**</span></span>
- <span data-ttu-id="97ff3-239">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="97ff3-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="97ff3-240">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="97ff3-240">**Submission type**</span></span>

<span data-ttu-id="97ff3-241">В верхней части страницы вы можете ввести дату начала, дату окончания, а затем отфильтровать **их, указав** значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="97ff3-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="97ff3-242">Update</span><span class="sxs-lookup"><span data-stu-id="97ff3-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="97ff3-243">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="97ff3-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="97ff3-244">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="97ff3-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="97ff3-245">Отмена отправки пользователя</span><span class="sxs-lookup"><span data-stu-id="97ff3-245">Undo user submissions</span></span>

<span data-ttu-id="97ff3-246">Когда пользователь отправит подозрительный адрес электронной почты в настраиваемый почтовый ящик, пользователь и администратор не смогут отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="97ff3-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="97ff3-247">Если пользователь хочет восстановить электронную почту, он будет доступен для восстановления в папках "Удаленные" и "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="97ff3-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="97ff3-248">Передача сообщений в корпорацию Майкрософт из настраиваемого почтового ящика</span><span class="sxs-lookup"><span data-stu-id="97ff3-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="97ff3-249">Если вы настроили личный почтовый ящик для перехвата сообщений, отправленных пользователями, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="97ff3-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="97ff3-250">Это позволяет эффективно переместить пользователя в отправку администратором.</span><span class="sxs-lookup"><span data-stu-id="97ff3-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="97ff3-251">На вкладке **настраиваемый почтовый ящик** выберите в списке нужное сообщение, нажмите кнопку **действия** и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="97ff3-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="97ff3-252">**Очистка отчета**</span><span class="sxs-lookup"><span data-stu-id="97ff3-252">**Report clean**</span></span>
- <span data-ttu-id="97ff3-253">**Фишинг отчетов**</span><span class="sxs-lookup"><span data-stu-id="97ff3-253">**Report phishing**</span></span>
- <span data-ttu-id="97ff3-254">**Отправка отчетов о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="97ff3-254">**Report malware**</span></span>
- <span data-ttu-id="97ff3-255">**Отправка отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="97ff3-255">**Report spam**</span></span>

![Параметры на кнопке действие](../../media/user-submission-custom-mailbox-action-button.png)
