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
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288793"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d1c96-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d1c96-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d1c96-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d1c96-104">**Applies to**</span></span>
- [<span data-ttu-id="d1c96-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d1c96-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d1c96-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="d1c96-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="d1c96-107">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал отправки в Центре безопасности и соответствия требованиям & для отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт для проверки.</span><span class="sxs-lookup"><span data-stu-id="d1c96-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d1c96-108">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="d1c96-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="d1c96-109">**Проверка подлинности электронной** почты: сведения о том, прошла ли проверка подлинности электронной почты при ее доставке.</span><span class="sxs-lookup"><span data-stu-id="d1c96-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="d1c96-110">**Попадание в** политику: сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиенте, переопределив наши решения фильтра служб.</span><span class="sxs-lookup"><span data-stu-id="d1c96-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="d1c96-111">**Репутация и детонация полезной** нагрузки: анализ URL-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="d1c96-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="d1c96-112">**Анализ оклассов:** проверка, сделанная людьми, чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="d1c96-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1c96-113">Анализ репутации и детонации полезной нагрузки и оценки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="d1c96-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="d1c96-114">Сведения не могут выходить за пределы организации, если данные не должны выходить за пределы клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d1c96-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="d1c96-115">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d1c96-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d1c96-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d1c96-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d1c96-117">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d1c96-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d1c96-118">Чтобы перейти непосредственно на **страницу отправки,** используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="d1c96-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="d1c96-119">Для отправки сообщений и файлов в корпорацию Майкрософт необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d1c96-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="d1c96-120">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d1c96-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="d1c96-121">**Управление организацией** в [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="d1c96-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="d1c96-122">Обратите внимание, что членство в [](#view-user-submissions-to-the-custom-mailbox) этой группе ролей необходимо для просмотра от отправленных пользователями сообщений в настраиваемый почтовый ящик, как описано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d1c96-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="d1c96-123">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в корпорацию Майкрософт, см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d1c96-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="d1c96-124">Сообщение о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d1c96-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="d1c96-125">В Центре безопасности & соответствия требованиям  перейдите в "Отправки управления угрозами", убедитесь, что вы на вкладке "Отправки администратора" и нажмите кнопку "Новая \>  **отправка".** </span><span class="sxs-lookup"><span data-stu-id="d1c96-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="d1c96-126">Используйте **новый flyout** отправки, который отображается для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d1c96-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d1c96-127">Отправка сомнительным электронных писем в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d1c96-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="d1c96-128">В разделе **"Тип объекта"** выберите "Электронная **почта".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="d1c96-129">В разделе **"Формат отправки"** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d1c96-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="d1c96-130">**ИД** сетевого сообщения: это значение GUID, доступное в загодре **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **x-MS-Office365-Filtering-Correlation-Id** в сообщениях, на карантине.</span><span class="sxs-lookup"><span data-stu-id="d1c96-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="d1c96-131">**File**: Click **Choose file**.</span><span class="sxs-lookup"><span data-stu-id="d1c96-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="d1c96-132">В открываемом диалоговом окле найдите и выберите EML-или MSG-файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1c96-133">Администраторы Защитника Office 365 (план 1) или плана 2 могут отправлять сообщения в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d1c96-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="d1c96-134">Другие администраторы смогут вернуться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="d1c96-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="d1c96-135">В разделе **"Получатели"** укажите одного или несколько получателей, для них необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="d1c96-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="d1c96-136">При проверке политики будет определяться, обошла ли электронная почта сканирование из-за политик пользователей или организаций.</span><span class="sxs-lookup"><span data-stu-id="d1c96-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="d1c96-137">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d1c96-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d1c96-138">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="d1c96-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d1c96-139">**Должен быть заблокирован:** выберите **"Спам",** **"Фишинг"** или "Вредоносная **программа".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="d1c96-140">Если вы не уверены, воспользуйтесь лучшим решением.</span><span class="sxs-lookup"><span data-stu-id="d1c96-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="d1c96-141">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-141">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d1c96-143">Отправка подозрительного URL-адреса в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d1c96-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="d1c96-144">В разделе **"Тип объекта"** выберите **URL-адрес.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="d1c96-145">В поле, которое появляется, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="d1c96-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="d1c96-146">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d1c96-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d1c96-147">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="d1c96-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d1c96-148">**Должно быть заблокировано:** выберите **"Фишинг"** или "Вредоносные **программы".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="d1c96-149">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-149">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="d1c96-151">Отправка подозрительного файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d1c96-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="d1c96-152">В разделе **"Тип объекта"** выберите **"Вложение".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="d1c96-153">Нажмите **кнопку "Выбрать файл"**.</span><span class="sxs-lookup"><span data-stu-id="d1c96-153">Click **Choose File**.</span></span> <span data-ttu-id="d1c96-154">В открываемом диалоговом окте найдите и выберите файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="d1c96-155">В разделе **"Причина отправки"** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d1c96-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d1c96-156">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="d1c96-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d1c96-157">**Должно быть заблокировано:** **вредоносные** программы — единственный вариант, который выбирается автоматически.</span><span class="sxs-lookup"><span data-stu-id="d1c96-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="d1c96-158">После завершения нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-158">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки вложения](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="d1c96-160">Просмотр от отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="d1c96-160">View admin submissions</span></span>

<span data-ttu-id="d1c96-161">В Центре безопасности & соответствия требованиям  перейдите в "Отправки управления угрозами", убедитесь, что вы на вкладке "Отправки администратора" и нажмите кнопку "Новая \>  **отправка".** </span><span class="sxs-lookup"><span data-stu-id="d1c96-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="d1c96-162">В верхней части страницы можно ввести даты начала, окончания и (по умолчанию) фильтровать по ИД отправки **(значение** GUID, назначенное каждой отправке), введите значение в поле и нажмите кнопку "Обновить". ![ ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="d1c96-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d1c96-163">Update</span><span class="sxs-lookup"><span data-stu-id="d1c96-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d1c96-164">Чтобы изменить критерии фильтрации, нажмите кнопку **"ИД отправки"** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d1c96-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="d1c96-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d1c96-165">**Sender**</span></span>
- <span data-ttu-id="d1c96-166">**Subject/URL/File name**</span><span class="sxs-lookup"><span data-stu-id="d1c96-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="d1c96-167">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="d1c96-167">**Submitted by**</span></span>
- <span data-ttu-id="d1c96-168">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-168">**Submission type**</span></span>
- <span data-ttu-id="d1c96-169">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d1c96-169">**Status**</span></span>

![Параметры фильтрации для от отправленных администратором сообщений](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="d1c96-171">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d1c96-172">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d1c96-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="d1c96-173">Под графиком три вкладки: **электронная** почта (по умолчанию), **URL-адрес** и **вложение.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="d1c96-174">Просмотр от отправленных сообщений электронной почты администратора</span><span class="sxs-lookup"><span data-stu-id="d1c96-174">View admin email submissions</span></span>

<span data-ttu-id="d1c96-175">Перейдите на **вкладку "Электронная** почта".</span><span class="sxs-lookup"><span data-stu-id="d1c96-175">Click the **Email** tab.</span></span>

<span data-ttu-id="d1c96-176">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="d1c96-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d1c96-177">**Дата**</span><span class="sxs-lookup"><span data-stu-id="d1c96-177">**Date**</span></span>
- <span data-ttu-id="d1c96-178">**ИД отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="d1c96-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="d1c96-179">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-180">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d1c96-181">**Sender**</span></span>
- <span data-ttu-id="d1c96-182">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-183">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-183">**Submission type**</span></span>
- <span data-ttu-id="d1c96-184">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-184">**Delivery reason**</span></span>
- <span data-ttu-id="d1c96-185">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d1c96-186"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="d1c96-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="d1c96-187">Сведения о повторном скане отправки администратора</span><span class="sxs-lookup"><span data-stu-id="d1c96-187">Admin submission rescan details</span></span>

<span data-ttu-id="d1c96-188">Сообщения, отправленные в отправках администратора, повторно сканируется и результаты показаны во flyout сведений:</span><span class="sxs-lookup"><span data-stu-id="d1c96-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="d1c96-189">Если в проверке подлинности электронной почты отправитель не был сбой во время доставки.</span><span class="sxs-lookup"><span data-stu-id="d1c96-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="d1c96-190">Сведения о любых политиках, которые могли повлиять на или переопредить заключение сообщения.</span><span class="sxs-lookup"><span data-stu-id="d1c96-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="d1c96-191">Текущие результаты детонации показывают, являются ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными.</span><span class="sxs-lookup"><span data-stu-id="d1c96-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="d1c96-192">Отзывы от оклассов.</span><span class="sxs-lookup"><span data-stu-id="d1c96-192">Feedback from graders.</span></span>

<span data-ttu-id="d1c96-193">Если переопределения найдены, повторное повторное сканировать должно пройти несколько минут.</span><span class="sxs-lookup"><span data-stu-id="d1c96-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="d1c96-194">Если при проверке подлинности или доставке электронной почты не возникла проблема с переопределением, то отзыв от оклассов может занять до дня.</span><span class="sxs-lookup"><span data-stu-id="d1c96-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="d1c96-195">Просмотр от отправленных URL-адресов администраторов</span><span class="sxs-lookup"><span data-stu-id="d1c96-195">View admin URL submissions</span></span>

<span data-ttu-id="d1c96-196">Щелкните **вкладку "URL-адрес".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-196">Click the **URL** tab.</span></span>

<span data-ttu-id="d1c96-197">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="d1c96-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d1c96-198">**Дата**</span><span class="sxs-lookup"><span data-stu-id="d1c96-198">**Date**</span></span>
- <span data-ttu-id="d1c96-199">**ИД отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-199">**Submission ID**</span></span>
- <span data-ttu-id="d1c96-200">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-202">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-202">**Submission type**</span></span>
- <span data-ttu-id="d1c96-203">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d1c96-204"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="d1c96-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="d1c96-205">Просмотр отложенных вложений администратора</span><span class="sxs-lookup"><span data-stu-id="d1c96-205">View admin attachment submissions</span></span>

<span data-ttu-id="d1c96-206">Перейдите **на вкладку "Вложения".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="d1c96-207">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="d1c96-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d1c96-208">**Дата**</span><span class="sxs-lookup"><span data-stu-id="d1c96-208">**Date**</span></span>
- <span data-ttu-id="d1c96-209">**ИД отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-209">**Submission ID**</span></span>
- <span data-ttu-id="d1c96-210">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-211">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-212">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-212">**Submission type**</span></span>
- <span data-ttu-id="d1c96-213">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d1c96-214"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="d1c96-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="d1c96-215">Просмотр от отправленных пользователями данных в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d1c96-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="d1c96-216">Если вы развернули надстройку [Report Message,](enable-the-report-message-add-in.md)надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенные отчеты в Outlook в  [Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие пользователи сообщают на вкладке "Отправки пользователей".</span><span class="sxs-lookup"><span data-stu-id="d1c96-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="d1c96-217">В Центре безопасности & соответствия требованиям перейдите **к** отправкам управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="d1c96-218">Выберите **вкладку "Отправки пользователей"** и нажмите кнопку **"Новая отправка".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="d1c96-219">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="d1c96-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d1c96-220">**Отправлено в**</span><span class="sxs-lookup"><span data-stu-id="d1c96-220">**Submitted on**</span></span>
- <span data-ttu-id="d1c96-221">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-222">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d1c96-223">**Sender**</span></span>
- <span data-ttu-id="d1c96-224">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-225">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-225">**Submission type**</span></span>

<span data-ttu-id="d1c96-226"><sup>\*</sup> Если щелкнуть это значение, подробные сведения будут отображаться во flyout.</span><span class="sxs-lookup"><span data-stu-id="d1c96-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="d1c96-227">В верхней части страницы можно ввести даты начала, окончания и (по  умолчанию) фильтровать по отправителю, введите значение в поле и нажмите кнопку ![ "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="d1c96-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d1c96-228">Update</span><span class="sxs-lookup"><span data-stu-id="d1c96-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d1c96-229">Чтобы изменить условия фильтрации, нажмите кнопку **"Отправитель"** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d1c96-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="d1c96-230">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="d1c96-230">**Sender domain**</span></span>
- <span data-ttu-id="d1c96-231">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d1c96-231">**Subject**</span></span>
- <span data-ttu-id="d1c96-232">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="d1c96-232">**Submitted by**</span></span>
- <span data-ttu-id="d1c96-233">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-233">**Submission type**</span></span>
- <span data-ttu-id="d1c96-234">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="d1c96-234">**Sender IP**</span></span>

![Параметры фильтрации для отправки пользователей](../../media/user-submissions-filter-options.png)

<span data-ttu-id="d1c96-236">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d1c96-237">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d1c96-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="d1c96-238">Просмотр от отправленных пользователями сообщений в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="d1c96-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="d1c96-239">**Если** вы [настроили](user-submission.md) пользовательский почтовый ящик для получения сообщений, сообщаемых пользователем, вы можете просматривать и отправлять сообщения, доставленные в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="d1c96-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="d1c96-240">В Центре безопасности & соответствия требованиям перейдите **к** отправкам управления \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="d1c96-241">Выберите **вкладку "Настраиваемый почтовый ящик".**</span><span class="sxs-lookup"><span data-stu-id="d1c96-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="d1c96-242">Вы можете нажать кнопку **"Параметры** столбца" в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="d1c96-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d1c96-243">**Отправлено в**</span><span class="sxs-lookup"><span data-stu-id="d1c96-243">**Submitted on**</span></span>
- <span data-ttu-id="d1c96-244">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-245">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d1c96-246">**Sender**</span></span>
- <span data-ttu-id="d1c96-247">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d1c96-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d1c96-248">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d1c96-248">**Submission type**</span></span>

<span data-ttu-id="d1c96-249">В верхней части страницы можно ввести даты начала, даты  окончания и фильтровать их, введите значение в поле и нажмите кнопку ![ "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="d1c96-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d1c96-250">Update</span><span class="sxs-lookup"><span data-stu-id="d1c96-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d1c96-251">Чтобы экспортировать результаты, щелкните **"Экспорт"** в верхней части страницы и выберите данные **диаграммы** или **таблицы.**</span><span class="sxs-lookup"><span data-stu-id="d1c96-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d1c96-252">В от появляются диалоговое окно сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d1c96-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="d1c96-253">Отмена пользовательских отгрузок</span><span class="sxs-lookup"><span data-stu-id="d1c96-253">Undo user submissions</span></span>

<span data-ttu-id="d1c96-254">После отправки подозрительного сообщения электронной почты в настраиваемый почтовый ящик у пользователя и администратора не будет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="d1c96-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="d1c96-255">Если пользователь хочет восстановить сообщение электронной почты, оно будет доступно для восстановления в папках "Удаленные" или "Нежелавая почта".</span><span class="sxs-lookup"><span data-stu-id="d1c96-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="d1c96-256">Отправка сообщений в корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="d1c96-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="d1c96-257">Если вы настроили пользовательский почтовый ящик для перехвата сообщений, сообщаемых пользователем, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="d1c96-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="d1c96-258">Это фактически перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="d1c96-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="d1c96-259">На **вкладке "Настраиваемый почтовый ящик"** выберите  сообщение в списке, нажмите кнопку "Действие" и выберите один из следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="d1c96-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="d1c96-260">**Отчет "чистый"**</span><span class="sxs-lookup"><span data-stu-id="d1c96-260">**Report clean**</span></span>
- <span data-ttu-id="d1c96-261">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="d1c96-261">**Report phishing**</span></span>
- <span data-ttu-id="d1c96-262">**Сообщить о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="d1c96-262">**Report malware**</span></span>
- <span data-ttu-id="d1c96-263">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="d1c96-263">**Report spam**</span></span>

![Параметры кнопки "Действие"](../../media/user-submission-custom-mailbox-action-button.png)
