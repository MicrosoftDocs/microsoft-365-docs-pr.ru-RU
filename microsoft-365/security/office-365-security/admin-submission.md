---
title: Отправки администратора
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
description: Администраторы могут узнать, как использовать портал отправки в Центре безопасности и & соответствия требованиям для отправки подозрительных сообщений, подозрительных фишинговых сообщений, спама и других потенциально опасных сообщений, URL-адресов и файлов корпорации Майкрософт для проверки.
ms.openlocfilehash: 432a245530d7906ae8babbc54176480d36315351
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864952"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c90fd-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c90fd-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c90fd-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал отправки в Центре безопасности и соответствия требованиям & для отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="c90fd-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c90fd-105">При отправке сообщения электронной почты вы получите сведения обо всех политиках, которые могли разрешить входящие сообщения электронной почты в клиенте, а также сведения об URL-адресах и вложениях в сообщении.</span><span class="sxs-lookup"><span data-stu-id="c90fd-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="c90fd-106">Политики, которые могли разрешить почту, включают список надежных отправитель отдельного пользователя, а также политики на уровне клиента, такие как правила потока почты Exchange (также известные как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="c90fd-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="c90fd-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c90fd-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c90fd-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c90fd-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c90fd-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c90fd-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c90fd-110">Чтобы перейти непосредственно на **страницу отправки,** используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="c90fd-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="c90fd-111">Для отправки сообщений и файлов в корпорацию Майкрософт необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="c90fd-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="c90fd-112">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c90fd-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="c90fd-113">**Управление организацией** в [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="c90fd-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="c90fd-114">Обратите внимание, что членство в [](#view-user-submissions-to-the-custom-mailbox) этой группе ролей необходимо для просмотра от отправленных пользователями сообщений в настраиваемый почтовый ящик, как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c90fd-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="c90fd-115">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в корпорацию Майкрософт, см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c90fd-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="c90fd-116">Сообщение о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c90fd-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="c90fd-117">В Центре безопасности & соответствия требованиям  перейдите в "Отправки управления угрозами", убедитесь, что вы на вкладке "Отправки администратора" и нажмите кнопку "Новая \>  **отправка".** </span><span class="sxs-lookup"><span data-stu-id="c90fd-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="c90fd-118">Используйте **новый flyout** отправки, который отображается для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c90fd-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c90fd-119">Отправка сомнительным электронных писем в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c90fd-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="c90fd-120">В разделе **"Тип объекта"** выберите "Электронная **почта".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="c90fd-121">В разделе **"Формат отправки"** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c90fd-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="c90fd-122">**ИД** сетевого сообщения: это значение GUID, доступное в загодре **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в загодровке **X-MS-Office365-Filtering-Correlation-Id** в сообщениях, на карантине.</span><span class="sxs-lookup"><span data-stu-id="c90fd-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="c90fd-123">**File**: Click **Choose file**.</span><span class="sxs-lookup"><span data-stu-id="c90fd-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="c90fd-124">В открываемом диалоговом окле найдите и выберите EML-или MSG-файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c90fd-125">Администраторы Защитника Office 365 (план 1) или плана 2 могут отправлять сообщения в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c90fd-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="c90fd-126">Другие администраторы смогут вернуться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="c90fd-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="c90fd-127">В разделе **"Получатели"** укажите одного или несколько получателей, для них необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="c90fd-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="c90fd-128">При проверке политики будет определяться, обошла ли электронная почта сканирование из-за политик пользователей или организаций.</span><span class="sxs-lookup"><span data-stu-id="c90fd-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="c90fd-129">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c90fd-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c90fd-130">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="c90fd-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c90fd-131">**Должен быть заблокирован:** выберите **"Спам",** **"Фишинг"** или "Вредоносная **программа".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="c90fd-132">Если вы не уверены, воспользуйтесь лучшим решением.</span><span class="sxs-lookup"><span data-stu-id="c90fd-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="c90fd-133">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-133">When you're finished, click the **Submit** button.</span></span>

![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c90fd-135">Отправка подозрительного URL-адреса в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c90fd-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="c90fd-136">В разделе **"Тип объекта"** выберите **URL-адрес.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="c90fd-137">В поле, которое появляется, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="c90fd-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="c90fd-138">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c90fd-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c90fd-139">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="c90fd-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c90fd-140">**Должно быть заблокировано:** выберите **"Фишинг"** или "Вредоносные **программы".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="c90fd-141">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-141">When you're finished, click the **Submit** button.</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="c90fd-143">Отправка подозрительного файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c90fd-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="c90fd-144">В разделе **"Тип объекта"** выберите **"Вложение".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="c90fd-145">Нажмите **кнопку "Выбрать файл"**.</span><span class="sxs-lookup"><span data-stu-id="c90fd-145">Click **Choose File**.</span></span> <span data-ttu-id="c90fd-146">В открываемом диалоговом окте найдите и выберите файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="c90fd-147">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c90fd-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c90fd-148">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="c90fd-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c90fd-149">**Должно быть заблокировано:** **вредоносная** программа является единственным выбором и выбирается автоматически.</span><span class="sxs-lookup"><span data-stu-id="c90fd-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="c90fd-150">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-150">When you're finished, click the **Submit** button.</span></span>

![Пример отправки вложения](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="c90fd-152">Просмотр от отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="c90fd-152">View admin submissions</span></span>

<span data-ttu-id="c90fd-153">В Центре безопасности & соответствия требованиям  перейдите в "Отправки управления угрозами", убедитесь, что вы на вкладке "Отправки администратора" и нажмите кнопку "Новая \>  **отправка".** </span><span class="sxs-lookup"><span data-stu-id="c90fd-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c90fd-154">В верхней части страницы можно ввести даты начала, окончания и (по умолчанию) фильтрацию по ИД отправки **(значение** GUID, назначенное каждой отправке), введите значение в поле и нажмите кнопку "Обновить". ![ ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="c90fd-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c90fd-155">Update</span><span class="sxs-lookup"><span data-stu-id="c90fd-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c90fd-156">Чтобы изменить критерии фильтрации, нажмите кнопку **"ИД отправки"** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c90fd-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="c90fd-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c90fd-157">**Sender**</span></span>
- <span data-ttu-id="c90fd-158">**Subject/URL/File name**</span><span class="sxs-lookup"><span data-stu-id="c90fd-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="c90fd-159">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="c90fd-159">**Submitted by**</span></span>
- <span data-ttu-id="c90fd-160">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-160">**Submission type**</span></span>
- <span data-ttu-id="c90fd-161">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c90fd-161">**Status**</span></span>

![Параметры фильтрации для от отправленных администратором сообщений](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="c90fd-163">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c90fd-164">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="c90fd-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="c90fd-165">Под графиком три вкладки: **электронная** почта (по умолчанию), **URL-адрес** и **вложение.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="c90fd-166">Просмотр от отправленных сообщений электронной почты администратора</span><span class="sxs-lookup"><span data-stu-id="c90fd-166">View admin email submissions</span></span>

<span data-ttu-id="c90fd-167">Перейдите на **вкладку "Электронная** почта".</span><span class="sxs-lookup"><span data-stu-id="c90fd-167">Click the **Email** tab.</span></span>

<span data-ttu-id="c90fd-168">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c90fd-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c90fd-169">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c90fd-169">**Date**</span></span>
- <span data-ttu-id="c90fd-170">**ИД отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="c90fd-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="c90fd-171">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-172">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c90fd-173">**Sender**</span></span>
- <span data-ttu-id="c90fd-174">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-175">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-175">**Submission type**</span></span>
- <span data-ttu-id="c90fd-176">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-176">**Delivery reason**</span></span>
- <span data-ttu-id="c90fd-177">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c90fd-178"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="c90fd-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="c90fd-179">Сведения о повторном скане отправки администратора</span><span class="sxs-lookup"><span data-stu-id="c90fd-179">Admin submission rescan details</span></span>

<span data-ttu-id="c90fd-180">Сообщения, отправленные в отправках администратора, повторно сканируется и результаты показаны во flyout сведений:</span><span class="sxs-lookup"><span data-stu-id="c90fd-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="c90fd-181">При сбое проверки подлинности электронной почты отправитель во время доставки.</span><span class="sxs-lookup"><span data-stu-id="c90fd-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="c90fd-182">Сведения о любых политиках, которые могли повлиять на или переопредить заключение сообщения.</span><span class="sxs-lookup"><span data-stu-id="c90fd-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="c90fd-183">Текущие результаты детонации показывают, являются ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными.</span><span class="sxs-lookup"><span data-stu-id="c90fd-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="c90fd-184">Отзывы от оклассов.</span><span class="sxs-lookup"><span data-stu-id="c90fd-184">Feedback from graders.</span></span>

<span data-ttu-id="c90fd-185">Если переопределения найдены, повторное повторное сканировать должно пройти несколько минут.</span><span class="sxs-lookup"><span data-stu-id="c90fd-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="c90fd-186">Если при проверке подлинности или доставке электронной почты не возникла проблема с переопределением, то отзыв от оклассов может занять до дня.</span><span class="sxs-lookup"><span data-stu-id="c90fd-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="c90fd-187">Просмотр от отправленных URL-адресов администратора</span><span class="sxs-lookup"><span data-stu-id="c90fd-187">View admin URL submissions</span></span>

<span data-ttu-id="c90fd-188">Щелкните **вкладку "URL-адрес".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-188">Click the **URL** tab.</span></span>

<span data-ttu-id="c90fd-189">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c90fd-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c90fd-190">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c90fd-190">**Date**</span></span>
- <span data-ttu-id="c90fd-191">**ИД отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-191">**Submission ID**</span></span>
- <span data-ttu-id="c90fd-192">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-194">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-194">**Submission type**</span></span>
- <span data-ttu-id="c90fd-195">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c90fd-196"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="c90fd-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="c90fd-197">Просмотр отложенных вложений администратора</span><span class="sxs-lookup"><span data-stu-id="c90fd-197">View admin attachment submissions</span></span>

<span data-ttu-id="c90fd-198">Перейдите **на вкладку "Вложения".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="c90fd-199">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c90fd-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c90fd-200">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c90fd-200">**Date**</span></span>
- <span data-ttu-id="c90fd-201">**ИД отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-201">**Submission ID**</span></span>
- <span data-ttu-id="c90fd-202">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-203">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-204">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-204">**Submission type**</span></span>
- <span data-ttu-id="c90fd-205">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c90fd-206"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="c90fd-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="c90fd-207">Просмотр от отправленных пользователями данных в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c90fd-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="c90fd-208">Если вы развернули надстройку [Report Message,](enable-the-report-message-add-in.md)надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенные отчеты в Outlook в  [Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие пользователи сообщают на вкладке "Отправки пользователей".</span><span class="sxs-lookup"><span data-stu-id="c90fd-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="c90fd-209">В Центре безопасности & соответствия требованиям перейдите **к** отправкам управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c90fd-210">Выберите **вкладку "Отправки пользователей"** и нажмите кнопку **"Новая отправка".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c90fd-211">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c90fd-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c90fd-212">**Отправлено в**</span><span class="sxs-lookup"><span data-stu-id="c90fd-212">**Submitted on**</span></span>
- <span data-ttu-id="c90fd-213">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-214">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c90fd-215">**Sender**</span></span>
- <span data-ttu-id="c90fd-216">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-217">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-217">**Submission type**</span></span>

<span data-ttu-id="c90fd-218"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="c90fd-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="c90fd-219">В верхней части страницы можно ввести даты начала, окончания и (по  умолчанию) фильтровать по отправителю, введите значение в поле и нажмите кнопку ![ "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="c90fd-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c90fd-220">Update</span><span class="sxs-lookup"><span data-stu-id="c90fd-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c90fd-221">Чтобы изменить критерии фильтрации, нажмите кнопку **"Отправитель"** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c90fd-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="c90fd-222">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="c90fd-222">**Sender domain**</span></span>
- <span data-ttu-id="c90fd-223">**Тема**</span><span class="sxs-lookup"><span data-stu-id="c90fd-223">**Subject**</span></span>
- <span data-ttu-id="c90fd-224">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="c90fd-224">**Submitted by**</span></span>
- <span data-ttu-id="c90fd-225">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-225">**Submission type**</span></span>
- <span data-ttu-id="c90fd-226">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="c90fd-226">**Sender IP**</span></span>

![Параметры фильтрации для отправки пользователей](../../media/user-submissions-filter-options.png)

<span data-ttu-id="c90fd-228">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c90fd-229">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="c90fd-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="c90fd-230">Просмотр от отправленных пользователем сообщений в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="c90fd-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="c90fd-231">**Если** вы [настроили](user-submission.md) пользовательский почтовый ящик для получения сообщений, сообщаемых пользователем, вы можете просматривать и отправлять сообщения, доставленные в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="c90fd-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="c90fd-232">В Центре безопасности & соответствия требованиям перейдите **к** отправкам управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c90fd-233">Выберите **вкладку "Настраиваемый почтовый ящик".**</span><span class="sxs-lookup"><span data-stu-id="c90fd-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="c90fd-234">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c90fd-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c90fd-235">**Отправлено в**</span><span class="sxs-lookup"><span data-stu-id="c90fd-235">**Submitted on**</span></span>
- <span data-ttu-id="c90fd-236">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-237">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c90fd-238">**Sender**</span></span>
- <span data-ttu-id="c90fd-239">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c90fd-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c90fd-240">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c90fd-240">**Submission type**</span></span>

<span data-ttu-id="c90fd-241">В верхней части страницы можно ввести даты начала, даты  окончания и фильтровать по отправленным, введите значение в поле и нажмите кнопку ![ "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="c90fd-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c90fd-242">Update</span><span class="sxs-lookup"><span data-stu-id="c90fd-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c90fd-243">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="c90fd-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c90fd-244">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="c90fd-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="c90fd-245">Отмена пользовательских отгрузок</span><span class="sxs-lookup"><span data-stu-id="c90fd-245">Undo user submissions</span></span>

<span data-ttu-id="c90fd-246">После отправки пользователем подозрительного сообщения электронной почты в настраиваемый почтовый ящик у пользователя и администратора не будет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="c90fd-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="c90fd-247">Если пользователь хочет восстановить сообщение электронной почты, оно будет доступно для восстановления в папках "Удаленные" или "Нежелавая почта".</span><span class="sxs-lookup"><span data-stu-id="c90fd-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="c90fd-248">Отправка сообщений в корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c90fd-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="c90fd-249">Если вы настроили пользовательский почтовый ящик для перехвата сообщений, сообщаемых пользователем, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="c90fd-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="c90fd-250">Это фактически перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="c90fd-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="c90fd-251">На **вкладке "Настраиваемый почтовый ящик"** выберите  сообщение в списке, нажмите кнопку "Действие" и выберите один из следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="c90fd-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="c90fd-252">**Отчет "чистый"**</span><span class="sxs-lookup"><span data-stu-id="c90fd-252">**Report clean**</span></span>
- <span data-ttu-id="c90fd-253">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="c90fd-253">**Report phishing**</span></span>
- <span data-ttu-id="c90fd-254">**Сообщить о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="c90fd-254">**Report malware**</span></span>
- <span data-ttu-id="c90fd-255">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="c90fd-255">**Report spam**</span></span>

![Параметры кнопки "Действие"](../../media/user-submission-custom-mailbox-action-button.png)
