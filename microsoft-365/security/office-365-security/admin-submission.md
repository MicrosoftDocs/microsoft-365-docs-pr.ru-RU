---
title: Отправки администратором
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать портал отправки в центре безопасности & соответствия требованиям для отправки подозрительных сообщений электронной почты, подозрительных сообщений фишинга, спама и других потенциально опасных сообщений, URL-адресов и файлов в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: ef401f34bb0bc7a9a9718443101924ad09bca8a0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947976"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="587a4-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="587a4-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="587a4-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал отправки в центре безопасности & соответствия требованиям для отправки электронных сообщений, URL-адресов и вложений в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="587a4-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="587a4-105">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="587a4-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="587a4-106">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="587a4-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="587a4-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="587a4-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="587a4-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="587a4-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="587a4-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="587a4-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="587a4-110">Чтобы перейти непосредственно на страницу **отправки** , используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="587a4-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="587a4-111">Чтобы передать сообщения и файлы в корпорацию Майкрософт, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="587a4-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="587a4-112">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="587a4-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="587a4-113">**Управление организацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="587a4-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="587a4-114">Обратите внимание, что членство в этой группе ролей необходимо для [просмотра отправки пользователей в пользовательский почтовый ящик](#view-user-submissions-to-the-custom-mailbox) , как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="587a4-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="587a4-115">Для получения дополнительных сведений о том, как пользователи могут отсылать сообщения и файлы в корпорацию Майкрософт, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="587a4-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="587a4-116">Сообщить о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="587a4-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="587a4-117">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** \> **Submissions**", убедитесь, что вы находитесь на вкладке " **отправленные администратором** ", а затем нажмите кнопку **создать отправку**.</span><span class="sxs-lookup"><span data-stu-id="587a4-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="587a4-118">Используйте всплывающее всплывающее окно **отправки** , которое появляется для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="587a4-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="587a4-119">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="587a4-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="587a4-120">В разделе **тип объекта** выберите **Электронная почта**.</span><span class="sxs-lookup"><span data-stu-id="587a4-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="587a4-121">В разделе **формат отправки** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="587a4-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="587a4-122">**Идентификатор сетевого сообщения**: это значение GUID, которое доступно в заголовке **X-MS-Exchange-Organization-Network-Message-ID** в сообщении.</span><span class="sxs-lookup"><span data-stu-id="587a4-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="587a4-123">**Файл**: нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="587a4-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="587a4-124">В открывшемся диалоговом окне найдите и выберите файл. EML или. MSG, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="587a4-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="587a4-125">В разделе **получатели** укажите одного или нескольких получателей, для которых необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="587a4-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="587a4-126">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="587a4-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="587a4-127">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="587a4-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="587a4-128">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="587a4-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="587a4-129">**Должны быть заблокированы**: выберите **спам**, **Фишинг**или **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="587a4-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="587a4-130">Если вы не уверены, используйте свои лучшие решения.</span><span class="sxs-lookup"><span data-stu-id="587a4-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="587a4-131">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="587a4-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="587a4-132">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="587a4-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="587a4-133">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="587a4-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="587a4-134">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="587a4-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="587a4-135">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="587a4-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="587a4-136">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="587a4-136">When you're finished, click the **Submit** button.</span></span>

![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="587a4-138">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="587a4-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="587a4-139">В разделе **тип объекта** выберите **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="587a4-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="587a4-140">В появившемся поле введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="587a4-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="587a4-141">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="587a4-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="587a4-142">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="587a4-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="587a4-143">**Должны быть заблокированы**: выберите **Фишинг** или **вредоносную**программу.</span><span class="sxs-lookup"><span data-stu-id="587a4-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="587a4-144">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="587a4-144">When you're finished, click the **Submit** button.</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="587a4-146">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="587a4-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="587a4-147">В разделе **тип объекта** выберите **вложение**.</span><span class="sxs-lookup"><span data-stu-id="587a4-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="587a4-148">Нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="587a4-148">Click **Choose File**.</span></span> <span data-ttu-id="587a4-149">В открывшемся диалоговом окне найдите и выберите файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="587a4-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="587a4-150">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="587a4-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="587a4-151">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="587a4-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="587a4-152">**Должны быть заблокированы**: **единственным** выбором и автоматически выбрано значение...</span><span class="sxs-lookup"><span data-stu-id="587a4-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="587a4-153">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="587a4-153">When you're finished, click the **Submit** button.</span></span>

![Пример отправки вложений](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="587a4-155">Просмотр отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="587a4-155">View admin submissions</span></span>

<span data-ttu-id="587a4-156">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** \> **Submissions**", убедитесь, что вы находитесь на вкладке " **отправленные администратором** ", а затем нажмите кнопку **создать отправку**.</span><span class="sxs-lookup"><span data-stu-id="587a4-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="587a4-157">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **идентификатору отправки** (значение GUID, назначенное каждой отправке), введя значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="587a4-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="587a4-158">Update</span><span class="sxs-lookup"><span data-stu-id="587a4-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="587a4-159">Чтобы изменить условия фильтра, нажмите кнопку " **идентификатор отправки** " и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="587a4-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="587a4-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="587a4-160">**Sender**</span></span>
- <span data-ttu-id="587a4-161">**Тема/URL-адрес/имя файла**</span><span class="sxs-lookup"><span data-stu-id="587a4-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="587a4-162">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="587a4-162">**Submitted by**</span></span>
- <span data-ttu-id="587a4-163">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-163">**Submission type**</span></span>
- <span data-ttu-id="587a4-164">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="587a4-164">**Status**</span></span>

![Параметры фильтра для отправки администратором](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="587a4-166">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="587a4-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="587a4-167">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="587a4-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="587a4-168">Под диаграммой расположены три вкладки: **Электронная почта** (по умолчанию), **URL-адрес**и **вложение**.</span><span class="sxs-lookup"><span data-stu-id="587a4-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="587a4-169">Просмотр отправляемых по электронной почте сообщений администратора</span><span class="sxs-lookup"><span data-stu-id="587a4-169">View admin email submissions</span></span>

<span data-ttu-id="587a4-170">Перейдите на вкладку **Электронная почта** .</span><span class="sxs-lookup"><span data-stu-id="587a4-170">Click the **Email** tab.</span></span>

<span data-ttu-id="587a4-171">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="587a4-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="587a4-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="587a4-172">**Date**</span></span>
- <span data-ttu-id="587a4-173">**Идентификатор отправки**: значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="587a4-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="587a4-174">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-175">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="587a4-176">**Sender**</span></span>
- <span data-ttu-id="587a4-177">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-178">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-178">**Submission type**</span></span>
- <span data-ttu-id="587a4-179">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="587a4-179">**Delivery reason**</span></span>
- <span data-ttu-id="587a4-180">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-181">**Тип элемента управления**</span><span class="sxs-lookup"><span data-stu-id="587a4-181">**Control type**</span></span>
- <span data-ttu-id="587a4-182">**Источник элемента управления**</span><span class="sxs-lookup"><span data-stu-id="587a4-182">**Control source**</span></span>

  <span data-ttu-id="587a4-183"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="587a4-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="587a4-184">Просмотр отправок URL-адреса администратора</span><span class="sxs-lookup"><span data-stu-id="587a4-184">View admin URL submissions</span></span>

<span data-ttu-id="587a4-185">Перейдите на вкладку **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="587a4-185">Click the **URL** tab.</span></span>

<span data-ttu-id="587a4-186">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="587a4-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="587a4-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="587a4-187">**Date**</span></span>
- <span data-ttu-id="587a4-188">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-188">**Submission ID**</span></span>
- <span data-ttu-id="587a4-189">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-191">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-191">**Submission type**</span></span>
- <span data-ttu-id="587a4-192">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="587a4-193"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="587a4-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="587a4-194">Просмотр отправки вложений администратора</span><span class="sxs-lookup"><span data-stu-id="587a4-194">View admin attachment submissions</span></span>

<span data-ttu-id="587a4-195">Перейдите на вкладку **вложения** .</span><span class="sxs-lookup"><span data-stu-id="587a4-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="587a4-196">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="587a4-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="587a4-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="587a4-197">**Date**</span></span>
- <span data-ttu-id="587a4-198">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-198">**Submission ID**</span></span>
- <span data-ttu-id="587a4-199">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-200">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-201">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-201">**Submission type**</span></span>
- <span data-ttu-id="587a4-202">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="587a4-203"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="587a4-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="587a4-204">Просмотр отправленных пользователем данных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="587a4-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="587a4-205">Если вы развернули [надстройку "сообщение отчета](enable-the-report-message-add-in.md)" или используете [встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), вы можете увидеть, какие пользователи будут создавать отчеты на вкладке " **Отправленные пользователем** ".</span><span class="sxs-lookup"><span data-stu-id="587a4-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="587a4-206">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** " \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="587a4-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="587a4-207">Выберите вкладку **отправки пользователей** и нажмите кнопку **создать отправку**.</span><span class="sxs-lookup"><span data-stu-id="587a4-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="587a4-208">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="587a4-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="587a4-209">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="587a4-209">**Submitted on**</span></span>
- <span data-ttu-id="587a4-210">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-211">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="587a4-212">**Sender**</span></span>
- <span data-ttu-id="587a4-213">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-214">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-214">**Submission type**</span></span>

<span data-ttu-id="587a4-215"><sup>\*</sup> Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="587a4-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="587a4-216">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **отправителю** , указав значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="587a4-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="587a4-217">Update</span><span class="sxs-lookup"><span data-stu-id="587a4-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="587a4-218">Чтобы изменить условия фильтра, нажмите кнопку **отправитель** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="587a4-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="587a4-219">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="587a4-219">**Sender domain**</span></span>
- <span data-ttu-id="587a4-220">**Тема**</span><span class="sxs-lookup"><span data-stu-id="587a4-220">**Subject**</span></span>
- <span data-ttu-id="587a4-221">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="587a4-221">**Submitted by**</span></span>
- <span data-ttu-id="587a4-222">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-222">**Submission type**</span></span>
- <span data-ttu-id="587a4-223">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="587a4-223">**Sender IP**</span></span>

![Параметры фильтра для отправки пользователя](../../media/user-submissions-filter-options.png)

<span data-ttu-id="587a4-225">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="587a4-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="587a4-226">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="587a4-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="587a4-227">Просмотр отправленных пользователем данных в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="587a4-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="587a4-228">**Если** вы [настроили настраиваемый почтовый ящик](user-submission.md) для получения сообщений, отправленных пользователями, вы можете просматривать и отправлять сообщения, которые были доставлены в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="587a4-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="587a4-229">В центре безопасности & соответствия требованиям перейдите к разделу " **Управление угрозами** " \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="587a4-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="587a4-230">Перейдите на вкладку **настраиваемый почтовый ящик** .</span><span class="sxs-lookup"><span data-stu-id="587a4-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="587a4-231">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="587a4-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="587a4-232">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="587a4-232">**Submitted on**</span></span>
- <span data-ttu-id="587a4-233">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-234">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="587a4-235">**Sender**</span></span>
- <span data-ttu-id="587a4-236">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="587a4-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="587a4-237">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="587a4-237">**Submission type**</span></span>

<span data-ttu-id="587a4-238">В верхней части страницы вы можете ввести дату начала, дату окончания, а затем отфильтровать **их, указав** значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="587a4-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="587a4-239">Update</span><span class="sxs-lookup"><span data-stu-id="587a4-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="587a4-240">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="587a4-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="587a4-241">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="587a4-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="587a4-242">Передача сообщений в корпорацию Майкрософт из настраиваемого почтового ящика</span><span class="sxs-lookup"><span data-stu-id="587a4-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="587a4-243">Если вы настроили личный почтовый ящик для перехвата сообщений, отправленных пользователями, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="587a4-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="587a4-244">Это позволяет эффективно переместить пользователя в отправку администратором.</span><span class="sxs-lookup"><span data-stu-id="587a4-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="587a4-245">На вкладке **настраиваемый почтовый ящик** выберите в списке нужное сообщение, нажмите кнопку **действия** и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="587a4-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="587a4-246">**Очистка отчета**</span><span class="sxs-lookup"><span data-stu-id="587a4-246">**Report clean**</span></span>
- <span data-ttu-id="587a4-247">**Фишинг отчетов**</span><span class="sxs-lookup"><span data-stu-id="587a4-247">**Report phishing**</span></span>
- <span data-ttu-id="587a4-248">**Отправка отчетов о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="587a4-248">**Report malware**</span></span>
- <span data-ttu-id="587a4-249">**Отправка отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="587a4-249">**Report spam**</span></span>

![Параметры на кнопке действие](../../media/user-submission-custom-mailbox-action-button.png)
