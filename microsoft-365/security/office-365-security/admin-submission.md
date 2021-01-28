---
title: Отправки администратора
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут научиться использовать портал отправки в Центре безопасности и & соответствия требованиям для отправки подозрительных сообщений, подозрительных фишинговых сообщений, спама и других потенциально опасных сообщений, URL-адресов и файлов корпорации Майкрософт для проверки.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029518"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5c90d-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c90d-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5c90d-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал отправки в Центре безопасности и соответствия требованиям & для отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="5c90d-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5c90d-105">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="5c90d-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="5c90d-106">**Проверка подлинности электронной** почты: сведения о том, прошла ли проверка подлинности электронной почты при ее доставке.</span><span class="sxs-lookup"><span data-stu-id="5c90d-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="5c90d-107">**Попадание в** политику: сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиенте, переопределив наши решения фильтра служб.</span><span class="sxs-lookup"><span data-stu-id="5c90d-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="5c90d-108">**Репутация и детонация полезной** нагрузки: анализ URL-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="5c90d-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="5c90d-109">**Анализ оклассов:** проверка, сделанная людьми, чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="5c90d-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c90d-110">Анализ репутации и детонации полезной нагрузки и оценки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="5c90d-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="5c90d-111">Сведения не могут выходить за пределы организации, если данные не должны выходить за пределы клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5c90d-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="5c90d-112">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5c90d-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5c90d-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5c90d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5c90d-114">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5c90d-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5c90d-115">Чтобы перейти непосредственно на **страницу отправки,** используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="5c90d-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="5c90d-116">Для отправки сообщений и файлов в корпорацию Майкрософт необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="5c90d-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="5c90d-117">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5c90d-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="5c90d-118">**Управление организацией** в [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="5c90d-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="5c90d-119">Обратите внимание, что членство в [](#view-user-submissions-to-the-custom-mailbox) этой группе ролей необходимо для просмотра от отправленных пользователями сообщений в настраиваемый почтовый ящик, как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5c90d-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="5c90d-120">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в корпорацию Майкрософт, см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5c90d-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="5c90d-121">Сообщение о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c90d-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="5c90d-122">В Центре безопасности & соответствия требованиям  перейдите в "Отправки управления угрозами", убедитесь, что вы на вкладке "Отправки администратора" и нажмите кнопку "Новая \>  **отправка".** </span><span class="sxs-lookup"><span data-stu-id="5c90d-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="5c90d-123">Используйте **новый flyout** отправки, который отображается для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="5c90d-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5c90d-124">Отправка сомнительным электронных писем в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c90d-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="5c90d-125">В разделе **"Тип объекта"** выберите "Электронная **почта".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="5c90d-126">В разделе **"Формат отправки"** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5c90d-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="5c90d-127">**ИД** сетевого сообщения: это значение GUID, доступное в загодре **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **x-MS-Office365-Filtering-Correlation-Id** в сообщениях, на карантине.</span><span class="sxs-lookup"><span data-stu-id="5c90d-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="5c90d-128">**File**: Click **Choose file**.</span><span class="sxs-lookup"><span data-stu-id="5c90d-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="5c90d-129">В открываемом диалоговом окле найдите и выберите EML-или MSG-файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5c90d-130">Администраторы Защитника Office 365 (план 1) или плана 2 могут отправлять сообщения в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="5c90d-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="5c90d-131">Другие администраторы смогут вернуться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="5c90d-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="5c90d-132">В разделе **"Получатели"** укажите одного или несколько получателей, для них необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="5c90d-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="5c90d-133">Проверка политики определяет, обошла ли почта сканирование из-за политик пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="5c90d-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="5c90d-134">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5c90d-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5c90d-135">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="5c90d-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5c90d-136">**Должен быть заблокирован:** выберите **"Спам",** **"Фишинг"** или "Вредоносная **программа".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="5c90d-137">Если вы не уверены, воспользуйтесь лучшими решениями.</span><span class="sxs-lookup"><span data-stu-id="5c90d-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="5c90d-138">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-138">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5c90d-140">Отправка подозрительного URL-адреса в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c90d-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="5c90d-141">В разделе **"Тип объекта"** выберите **URL-адрес.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="5c90d-142">В поле, которое появляется, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="5c90d-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="5c90d-143">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5c90d-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5c90d-144">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="5c90d-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5c90d-145">**Должно быть заблокировано:** выберите **"Фишинг"** или "Вредоносные **программы".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="5c90d-146">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-146">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="5c90d-148">Отправка подозрительного файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c90d-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="5c90d-149">В разделе **"Тип объекта"** выберите **"Вложение".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="5c90d-150">Нажмите **кнопку "Выбрать файл"**.</span><span class="sxs-lookup"><span data-stu-id="5c90d-150">Click **Choose File**.</span></span> <span data-ttu-id="5c90d-151">В открываемом диалоговом окте найдите и выберите файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="5c90d-152">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5c90d-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5c90d-153">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="5c90d-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5c90d-154">**Должно быть заблокировано:** **вредоносная** программа является единственным выбором и выбирается автоматически.</span><span class="sxs-lookup"><span data-stu-id="5c90d-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="5c90d-155">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-155">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки вложения](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="5c90d-157">Просмотр от отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="5c90d-157">View admin submissions</span></span>

<span data-ttu-id="5c90d-158">В Центре безопасности & соответствия требованиям  перейдите в "Отправки управления угрозами", убедитесь, что вы на вкладке "Отправки администратора" и нажмите кнопку "Новая \>  **отправка".** </span><span class="sxs-lookup"><span data-stu-id="5c90d-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="5c90d-159">В верхней части страницы можно ввести даты начала, окончания и (по умолчанию) фильтровать по ИД отправки **(значение** GUID, назначенное каждой отправке), введите значение в поле и нажмите кнопку "Обновить". ![ ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="5c90d-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5c90d-160">Update</span><span class="sxs-lookup"><span data-stu-id="5c90d-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5c90d-161">Чтобы изменить условия фильтрации, нажмите кнопку **"ИД отправки"** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="5c90d-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="5c90d-162">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5c90d-162">**Sender**</span></span>
- <span data-ttu-id="5c90d-163">**Subject/URL/File name**</span><span class="sxs-lookup"><span data-stu-id="5c90d-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="5c90d-164">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="5c90d-164">**Submitted by**</span></span>
- <span data-ttu-id="5c90d-165">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-165">**Submission type**</span></span>
- <span data-ttu-id="5c90d-166">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="5c90d-166">**Status**</span></span>

![Параметры фильтрации для отправки администратором](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="5c90d-168">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5c90d-169">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="5c90d-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="5c90d-170">Под графиком три вкладки: **электронная** почта (по умолчанию), **URL-адрес** и **вложение.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="5c90d-171">Просмотр от отправленных сообщений электронной почты администратора</span><span class="sxs-lookup"><span data-stu-id="5c90d-171">View admin email submissions</span></span>

<span data-ttu-id="5c90d-172">Перейдите на **вкладку "Электронная** почта".</span><span class="sxs-lookup"><span data-stu-id="5c90d-172">Click the **Email** tab.</span></span>

<span data-ttu-id="5c90d-173">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="5c90d-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5c90d-174">**Дата**</span><span class="sxs-lookup"><span data-stu-id="5c90d-174">**Date**</span></span>
- <span data-ttu-id="5c90d-175">**ИД отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="5c90d-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="5c90d-176">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-177">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-178">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5c90d-178">**Sender**</span></span>
- <span data-ttu-id="5c90d-179">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-180">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-180">**Submission type**</span></span>
- <span data-ttu-id="5c90d-181">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-181">**Delivery reason**</span></span>
- <span data-ttu-id="5c90d-182">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5c90d-183"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="5c90d-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="5c90d-184">Сведения о повторном скане отправки администратора</span><span class="sxs-lookup"><span data-stu-id="5c90d-184">Admin submission rescan details</span></span>

<span data-ttu-id="5c90d-185">Сообщения, отправленные в отправках администратора, повторно сканируется и результаты показаны во flyout сведений:</span><span class="sxs-lookup"><span data-stu-id="5c90d-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="5c90d-186">Если в проверке подлинности электронной почты отправитель не был сбой во время доставки.</span><span class="sxs-lookup"><span data-stu-id="5c90d-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="5c90d-187">Сведения о любых политиках, которые могли повлиять на или переопредить заключение сообщения.</span><span class="sxs-lookup"><span data-stu-id="5c90d-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="5c90d-188">Текущие результаты детонации показывают, являются ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными.</span><span class="sxs-lookup"><span data-stu-id="5c90d-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="5c90d-189">Отзывы от оклассов.</span><span class="sxs-lookup"><span data-stu-id="5c90d-189">Feedback from graders.</span></span>

<span data-ttu-id="5c90d-190">Если переопределения найдены, повторное сканировать должно пройти несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5c90d-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="5c90d-191">Если переопределение не повлияло на проверку подлинности или доставку электронной почты, то отзывы о них могут занять до дня.</span><span class="sxs-lookup"><span data-stu-id="5c90d-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="5c90d-192">Просмотр от отправленных URL-адресов администратора</span><span class="sxs-lookup"><span data-stu-id="5c90d-192">View admin URL submissions</span></span>

<span data-ttu-id="5c90d-193">Щелкните **вкладку "URL-адрес".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-193">Click the **URL** tab.</span></span>

<span data-ttu-id="5c90d-194">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="5c90d-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5c90d-195">**Дата**</span><span class="sxs-lookup"><span data-stu-id="5c90d-195">**Date**</span></span>
- <span data-ttu-id="5c90d-196">**ИД отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-196">**Submission ID**</span></span>
- <span data-ttu-id="5c90d-197">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-199">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-199">**Submission type**</span></span>
- <span data-ttu-id="5c90d-200">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5c90d-201"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="5c90d-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="5c90d-202">Просмотр отложенных вложений администратора</span><span class="sxs-lookup"><span data-stu-id="5c90d-202">View admin attachment submissions</span></span>

<span data-ttu-id="5c90d-203">Перейдите **на вкладку "Вложения".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="5c90d-204">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="5c90d-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5c90d-205">**Дата**</span><span class="sxs-lookup"><span data-stu-id="5c90d-205">**Date**</span></span>
- <span data-ttu-id="5c90d-206">**ИД отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-206">**Submission ID**</span></span>
- <span data-ttu-id="5c90d-207">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-208">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-209">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-209">**Submission type**</span></span>
- <span data-ttu-id="5c90d-210">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5c90d-211"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="5c90d-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="5c90d-212">Просмотр от отправленных пользователями данных в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5c90d-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="5c90d-213">Если вы развернули надстройку [Report Message,](enable-the-report-message-add-in.md)надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенные отчеты в Outlook в  [Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие пользователи сообщают на вкладке "Отправки пользователей".</span><span class="sxs-lookup"><span data-stu-id="5c90d-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="5c90d-214">В Центре безопасности & соответствия требованиям перейдите **к** отправкам управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="5c90d-215">Выберите **вкладку "Отправки пользователей"** и нажмите кнопку **"Новая отправка".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="5c90d-216">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="5c90d-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5c90d-217">**Отправлено в**</span><span class="sxs-lookup"><span data-stu-id="5c90d-217">**Submitted on**</span></span>
- <span data-ttu-id="5c90d-218">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-219">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-220">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5c90d-220">**Sender**</span></span>
- <span data-ttu-id="5c90d-221">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-222">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-222">**Submission type**</span></span>

<span data-ttu-id="5c90d-223"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="5c90d-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="5c90d-224">В верхней части страницы можно ввести даты начала, окончания и (по  умолчанию) фильтровать по отправителю, введите значение в поле и нажмите кнопку ![ "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="5c90d-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5c90d-225">Update</span><span class="sxs-lookup"><span data-stu-id="5c90d-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5c90d-226">Чтобы изменить критерии фильтрации, нажмите кнопку **"Отправитель"** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="5c90d-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="5c90d-227">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="5c90d-227">**Sender domain**</span></span>
- <span data-ttu-id="5c90d-228">**Тема**</span><span class="sxs-lookup"><span data-stu-id="5c90d-228">**Subject**</span></span>
- <span data-ttu-id="5c90d-229">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="5c90d-229">**Submitted by**</span></span>
- <span data-ttu-id="5c90d-230">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-230">**Submission type**</span></span>
- <span data-ttu-id="5c90d-231">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="5c90d-231">**Sender IP**</span></span>

![Параметры фильтрации для отправки пользователей](../../media/user-submissions-filter-options.png)

<span data-ttu-id="5c90d-233">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5c90d-234">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="5c90d-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="5c90d-235">Просмотр от отправленных пользователями сообщений в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="5c90d-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="5c90d-236">**Если** вы [настроили](user-submission.md) пользовательский почтовый ящик для получения сообщений, сообщаемых пользователем, вы можете просматривать и отправлять сообщения, доставленные в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="5c90d-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="5c90d-237">В Центре безопасности & соответствия требованиям перейдите **к** отправкам управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="5c90d-238">Выберите **вкладку "Настраиваемый почтовый ящик".**</span><span class="sxs-lookup"><span data-stu-id="5c90d-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="5c90d-239">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="5c90d-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5c90d-240">**Отправлено в**</span><span class="sxs-lookup"><span data-stu-id="5c90d-240">**Submitted on**</span></span>
- <span data-ttu-id="5c90d-241">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-242">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-243">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5c90d-243">**Sender**</span></span>
- <span data-ttu-id="5c90d-244">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c90d-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5c90d-245">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="5c90d-245">**Submission type**</span></span>

<span data-ttu-id="5c90d-246">В верхней части страницы можно ввести даты начала, даты  окончания и фильтровать их, введите значение в поле и нажмите кнопку ![ "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="5c90d-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5c90d-247">Update</span><span class="sxs-lookup"><span data-stu-id="5c90d-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5c90d-248">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="5c90d-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5c90d-249">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="5c90d-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="5c90d-250">Отмена отгрузок пользователей</span><span class="sxs-lookup"><span data-stu-id="5c90d-250">Undo user submissions</span></span>

<span data-ttu-id="5c90d-251">После отправки пользователем подозрительного сообщения электронной почты в настраиваемый почтовый ящик у пользователя и администратора не будет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="5c90d-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="5c90d-252">Если пользователь хочет восстановить сообщение электронной почты, оно будет доступно для восстановления в папках "Удаленные" или "Нежелавая почта".</span><span class="sxs-lookup"><span data-stu-id="5c90d-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="5c90d-253">Отправка сообщений в корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="5c90d-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="5c90d-254">Если вы настроили пользовательский почтовый ящик для перехвата сообщений, сообщаемых пользователем, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="5c90d-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="5c90d-255">Это фактически перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="5c90d-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="5c90d-256">На **вкладке "Настраиваемый почтовый ящик"** выберите  сообщение в списке, нажмите кнопку "Действие" и выберите один из следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="5c90d-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="5c90d-257">**Отчет "чистый"**</span><span class="sxs-lookup"><span data-stu-id="5c90d-257">**Report clean**</span></span>
- <span data-ttu-id="5c90d-258">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="5c90d-258">**Report phishing**</span></span>
- <span data-ttu-id="5c90d-259">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="5c90d-259">**Report malware**</span></span>
- <span data-ttu-id="5c90d-260">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="5c90d-260">**Report spam**</span></span>

![Параметры кнопки "Действие"](../../media/user-submission-custom-mailbox-action-button.png)
