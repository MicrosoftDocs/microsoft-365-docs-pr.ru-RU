---
title: Представления администратора
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
description: Администраторы могут узнать, как использовать портал Отправки в Центре соответствия требованиям & безопасности для отправки подозрительных сообщений электронной почты, подозрительных фишинговых сообщений, нежелательной почты и других потенциально вредных сообщений, URL-адресов и файлов в Корпорацию Майкрософт для сканирования.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96a5469b1093c71997747b2c4c3b49bc1964f72b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581074"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c9cae-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9cae-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c9cae-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="c9cae-104">**Applies to**</span></span>
- [<span data-ttu-id="c9cae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c9cae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c9cae-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="c9cae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="c9cae-107">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал Отправки в Центре обеспечения безопасности & для отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="c9cae-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c9cae-108">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="c9cae-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="c9cae-109">**Проверка подлинности электронной** почты. Сведения о том, прошла ли проверка подлинности электронной почты при ее доставке или сбой.</span><span class="sxs-lookup"><span data-stu-id="c9cae-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="c9cae-110">**Хиты** политики. Сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиента, переопределив наши решения фильтра службы.</span><span class="sxs-lookup"><span data-stu-id="c9cae-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="c9cae-111">**Репутация и детонация полезной** нагрузки: проверка url-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="c9cae-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="c9cae-112">**Анализ грейдера.** Проверка, сделанная грейдерами,чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="c9cae-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9cae-113">Анализ репутации/детонации и грейдера полезной нагрузки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="c9cae-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="c9cae-114">Сведения не могут выходить за пределы организации, если данные не должны покидать границу клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c9cae-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="c9cae-115">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт см. в этой ссылке. [](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c9cae-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c9cae-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c9cae-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c9cae-117">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c9cae-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c9cae-118">Чтобы перейти непосредственно на **страницу Отправка,** используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="c9cae-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="c9cae-119">Чтобы отправить сообщения и файлы в Корпорацию Майкрософт, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="c9cae-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="c9cae-120">**Управление организацией** или **чтение** безопасности в Центре [& безопасности](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c9cae-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="c9cae-121">**Управление организацией** в [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c9cae-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="c9cae-122">Обратите внимание, что членство в [](#view-user-submissions-to-the-custom-mailbox) этой группе ролей необходимо для просмотра пользовательских представлений в настраиваемом почтовом ящике, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c9cae-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="c9cae-123">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в Корпорацию Майкрософт, см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c9cae-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="c9cae-124">Сообщение о подозрительном контенте в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9cae-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="c9cae-125">В Центре & безопасности перейдите к  отправкам управления угрозами, убедитесь, что вы на вкладке Отправки администратора, а затем нажмите \>  **кнопку Новая отправка**. </span><span class="sxs-lookup"><span data-stu-id="c9cae-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="c9cae-126">Используйте **новый флайет** отправки, который, как представляется, представляет сообщение, URL-адрес или вложение, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c9cae-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c9cae-127">Отправка сомнительного сообщения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9cae-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="c9cae-128">В разделе **Тип объекта** выберите **электронную почту**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="c9cae-129">В разделе **Формат отправки** используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c9cae-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="c9cae-130">Сетевой **ID** сообщения. Это значение GUID, доступное в загорелом загоне **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **загоне X-MS-Office365-Filtering-Correlation-Id** в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="c9cae-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="c9cae-131">**Файл:** Нажмите **выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="c9cae-132">В открываемом диалоговом окте найти и выбрать файл .eml или .msg, а затем нажмите **кнопку Открыть**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c9cae-133">Администраторы с Defender для Office 365 Plan 1 или Plan 2 могут отправлять сообщения в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c9cae-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="c9cae-134">Другие администраторы смогут возвращаться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="c9cae-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="c9cae-135">В разделе **Получатели** укажите одного или несколько получателей, против них необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="c9cae-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="c9cae-136">Проверка политики определяет, не обходится ли проверка электронной почты из-за политики пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="c9cae-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="c9cae-137">В разделе **Причина отправки** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c9cae-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c9cae-138">**Не должно было быть заблокировано**</span><span class="sxs-lookup"><span data-stu-id="c9cae-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c9cae-139">**Должны были быть заблокированы:** Выберите **спам,** **фишинг** или **вредоносные программы**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="c9cae-140">Если вы не уверены, используйте свои лучшие суждения.</span><span class="sxs-lookup"><span data-stu-id="c9cae-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="c9cae-141">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-141">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c9cae-143">Отправка подозрительного URL-адреса в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9cae-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="c9cae-144">В разделе **Тип объекта** выберите **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="c9cae-145">В поле, которое отображается, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="c9cae-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="c9cae-146">В разделе **Причина отправки** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c9cae-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c9cae-147">**Не должно было быть заблокировано**</span><span class="sxs-lookup"><span data-stu-id="c9cae-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c9cae-148">**Должны были быть заблокированы:** Выберите **фишинг** или **вредоносные программы**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="c9cae-149">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-149">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="c9cae-151">Отправка подозрительного файла в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9cae-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="c9cae-152">В разделе **Тип объекта** выберите **Вложение**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="c9cae-153">Нажмите **кнопку Выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-153">Click **Choose File**.</span></span> <span data-ttu-id="c9cae-154">В открываемом диалоговом окте найти и выбрать файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="c9cae-155">В разделе **Причина отправки** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c9cae-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c9cae-156">**Не должно было быть заблокировано**</span><span class="sxs-lookup"><span data-stu-id="c9cae-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c9cae-157">**Должны были быть заблокированы:** **вредоносные** программы является единственным выбором, и автоматически выбирается..</span><span class="sxs-lookup"><span data-stu-id="c9cae-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="c9cae-158">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-158">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки вложений](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="c9cae-160">Просмотр элементов, отправленных для анализа</span><span class="sxs-lookup"><span data-stu-id="c9cae-160">View items Submitted for analysis</span></span>

<span data-ttu-id="c9cae-161">В Центре & безопасности перейдите в **Службу** управления угрозами , убедитесь, что вы на вкладке \>  **Отправка для анализа**</span><span class="sxs-lookup"><span data-stu-id="c9cae-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="c9cae-162">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по представлению **ID** (значение GUID, назначенное каждой отправке), введите значение в поле и нажав кнопку ![ Обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="c9cae-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c9cae-163">Update</span><span class="sxs-lookup"><span data-stu-id="c9cae-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c9cae-164">Чтобы изменить критерии фильтрации, нажмите кнопку **Отправка ИД** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c9cae-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="c9cae-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c9cae-165">**Sender**</span></span>
- <span data-ttu-id="c9cae-166">**Имя subject/URL/File**</span><span class="sxs-lookup"><span data-stu-id="c9cae-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="c9cae-167">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="c9cae-167">**Submitted by**</span></span>
- <span data-ttu-id="c9cae-168">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-168">**Submission type**</span></span>
- <span data-ttu-id="c9cae-169">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c9cae-169">**Status**</span></span>

![Параметры фильтрации для представлений администратора](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="c9cae-171">Чтобы экспортировать результаты, щелкните **Экспорт** в верхней части страницы и выберите **диаграммы данных** или **таблицы**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c9cae-172">В диалоговом окте, который отображается, сохраните файл .csv.</span><span class="sxs-lookup"><span data-stu-id="c9cae-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="c9cae-173">Ниже графика приведены три вкладки: **электронная почта** (по умолчанию), **URL-адрес** и **вложение.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="c9cae-174">Просмотр сообщений электронной почты администратора</span><span class="sxs-lookup"><span data-stu-id="c9cae-174">View admin email submissions</span></span>

<span data-ttu-id="c9cae-175">Щелкните **вкладку Email.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-175">Click the **Email** tab.</span></span>

<span data-ttu-id="c9cae-176">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c9cae-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c9cae-177">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c9cae-177">**Date**</span></span>
- <span data-ttu-id="c9cae-178">**ID отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="c9cae-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="c9cae-179">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-180">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c9cae-181">**Sender**</span></span>
- <span data-ttu-id="c9cae-182">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-183">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-183">**Submission type**</span></span>
- <span data-ttu-id="c9cae-184">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-184">**Delivery reason**</span></span>
- <span data-ttu-id="c9cae-185">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c9cae-186"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="c9cae-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="c9cae-187">Сведения о повторном представлении администратора</span><span class="sxs-lookup"><span data-stu-id="c9cae-187">Admin submission rescan details</span></span>

<span data-ttu-id="c9cae-188">Сообщения, отправленные в представлениях администратора, rescanned и результаты, показанные в разлете деталей:</span><span class="sxs-lookup"><span data-stu-id="c9cae-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="c9cae-189">Возникновение сбоя при проверке подлинности электронной почты отправителя в момент доставки.</span><span class="sxs-lookup"><span data-stu-id="c9cae-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="c9cae-190">Сведения о любых совпадениях политик, которые могут повлиять на решение по безопасности касательно сообщения или переопределить его.</span><span class="sxs-lookup"><span data-stu-id="c9cae-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="c9cae-191">Текущие результаты отключения, чтобы определить, были ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными или нет.</span><span class="sxs-lookup"><span data-stu-id="c9cae-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="c9cae-192">Отзывы от грейдеров.</span><span class="sxs-lookup"><span data-stu-id="c9cae-192">Feedback from graders.</span></span>

<span data-ttu-id="c9cae-193">Если было обнаружено переопределение, повторное сканирование должно завершиться через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="c9cae-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="c9cae-194">Если в проверке подлинности или доставке электронной почты не возникло проблем с переопределением, то отзывы от грейдеров могут занять до одного дня.</span><span class="sxs-lookup"><span data-stu-id="c9cae-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="c9cae-195">Просмотр url-адресов администратора</span><span class="sxs-lookup"><span data-stu-id="c9cae-195">View admin URL submissions</span></span>

<span data-ttu-id="c9cae-196">Щелкните **вкладку** URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="c9cae-196">Click the **URL** tab.</span></span>

<span data-ttu-id="c9cae-197">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c9cae-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c9cae-198">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c9cae-198">**Date**</span></span>
- <span data-ttu-id="c9cae-199">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-199">**Submission ID**</span></span>
- <span data-ttu-id="c9cae-200">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-202">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-202">**Submission type**</span></span>
- <span data-ttu-id="c9cae-203">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c9cae-204"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="c9cae-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="c9cae-205">Просмотр представлений вложения администратора</span><span class="sxs-lookup"><span data-stu-id="c9cae-205">View admin attachment submissions</span></span>

<span data-ttu-id="c9cae-206">Щелкните **вкладку Вложения.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="c9cae-207">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c9cae-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c9cae-208">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c9cae-208">**Date**</span></span>
- <span data-ttu-id="c9cae-209">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-209">**Submission ID**</span></span>
- <span data-ttu-id="c9cae-210">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-211">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-212">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-212">**Submission type**</span></span>
- <span data-ttu-id="c9cae-213">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c9cae-214"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="c9cae-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="c9cae-215">Просмотр пользовательских представлений в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9cae-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="c9cae-216">Если вы развернули надстройку [Report Message,](enable-the-report-message-add-in.md)надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенную отчетность в [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)в  Интернете, вы можете увидеть, какие отчеты пользователи сообщают на вкладке Отправки пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9cae-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="c9cae-217">В Центре & безопасности перейдите в **службу управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c9cae-218">Выберите **вкладку Отправки** пользователя и нажмите кнопку **Новая отправка**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c9cae-219">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c9cae-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c9cae-220">**Отправлено на**</span><span class="sxs-lookup"><span data-stu-id="c9cae-220">**Submitted on**</span></span>
- <span data-ttu-id="c9cae-221">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-222">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c9cae-223">**Sender**</span></span>
- <span data-ttu-id="c9cae-224">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-225">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-225">**Submission type**</span></span>

<span data-ttu-id="c9cae-226"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="c9cae-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="c9cae-227">В верхней части страницы можно ввести дату начала, дату окончания и (по  умолчанию) фильтровать отправитель, введите значение в поле и нажав кнопку ![ Обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="c9cae-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c9cae-228">Update</span><span class="sxs-lookup"><span data-stu-id="c9cae-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c9cae-229">Чтобы изменить критерии фильтрации, нажмите кнопку **Отправитель** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="c9cae-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="c9cae-230">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="c9cae-230">**Sender domain**</span></span>
- <span data-ttu-id="c9cae-231">**Тема**</span><span class="sxs-lookup"><span data-stu-id="c9cae-231">**Subject**</span></span>
- <span data-ttu-id="c9cae-232">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="c9cae-232">**Submitted by**</span></span>
- <span data-ttu-id="c9cae-233">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-233">**Submission type**</span></span>
- <span data-ttu-id="c9cae-234">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="c9cae-234">**Sender IP**</span></span>

![Параметры фильтрации для отправки пользователей](../../media/user-submissions-filter-options.png)

<span data-ttu-id="c9cae-236">Чтобы экспортировать результаты, щелкните **Экспорт** в верхней части страницы и выберите **диаграммы данных** или **таблицы**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c9cae-237">В диалоговом окте, который отображается, сохраните файл .csv.</span><span class="sxs-lookup"><span data-stu-id="c9cae-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="c9cae-238">Просмотр пользовательских представлений в настраиваемом почтовом ящике</span><span class="sxs-lookup"><span data-stu-id="c9cae-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="c9cae-239">**Если** вы [настроили](user-submission.md) настраиваемый почтовый ящик для получения сообщений, сообщаемых пользователем, вы можете просматривать и отправлять сообщения, доставленные в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="c9cae-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="c9cae-240">В Центре & безопасности перейдите в **службу управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c9cae-241">Выберите **вкладку Настраиваемый почтовый ящик.**</span><span class="sxs-lookup"><span data-stu-id="c9cae-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="c9cae-242">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="c9cae-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c9cae-243">**Отправлено на**</span><span class="sxs-lookup"><span data-stu-id="c9cae-243">**Submitted on**</span></span>
- <span data-ttu-id="c9cae-244">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-245">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="c9cae-246">**Sender**</span></span>
- <span data-ttu-id="c9cae-247">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9cae-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c9cae-248">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="c9cae-248">**Submission type**</span></span>

<span data-ttu-id="c9cae-249">В верхней части страницы можно ввести дату начала, дату окончания  и отфильтровать ее, введите значение в поле и нажав кнопку ![ ](../../media/scc-quarantine-refresh.png) Обновить.</span><span class="sxs-lookup"><span data-stu-id="c9cae-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c9cae-250">Update</span><span class="sxs-lookup"><span data-stu-id="c9cae-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c9cae-251">Чтобы экспортировать результаты, щелкните **Экспорт** в верхней части страницы и выберите **диаграммы данных** или **таблицы**.</span><span class="sxs-lookup"><span data-stu-id="c9cae-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c9cae-252">В диалоговом окте, который отображается, сохраните файл .csv.</span><span class="sxs-lookup"><span data-stu-id="c9cae-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="c9cae-253">Если организации настроены на отправку только в настраиваемый почтовый ящик, сообщения не будут отправляться на rescan и результаты на портале сообщений пользователя всегда будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="c9cae-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="c9cae-254">Отмена отправки пользователей</span><span class="sxs-lookup"><span data-stu-id="c9cae-254">Undo user submissions</span></span>

<span data-ttu-id="c9cae-255">После отправки подозрительной электронной почты в настраиваемый почтовый ящик у пользователя и администратора нет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="c9cae-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="c9cae-256">Если пользователь хочет восстановить электронную почту, она будет доступна для восстановления в папках "Удаленные элементы" или "Нежелательной почты".</span><span class="sxs-lookup"><span data-stu-id="c9cae-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="c9cae-257">Отправка сообщений в Корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="c9cae-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="c9cae-258">Если настраивается настраиваемый почтовый ящик для перехвата сообщений, сообщаемых пользователями, без отправки сообщений в Корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="c9cae-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="c9cae-259">Это эффективно перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="c9cae-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="c9cae-260">На **вкладке Настраиваемый почтовый ящик** выберите сообщение в списке, нажмите кнопку **Действие** и сделайте один из следующих выборов:</span><span class="sxs-lookup"><span data-stu-id="c9cae-260">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="c9cae-261">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="c9cae-261">**Report clean**</span></span>
- <span data-ttu-id="c9cae-262">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="c9cae-262">**Report phishing**</span></span>
- <span data-ttu-id="c9cae-263">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="c9cae-263">**Report malware**</span></span>
- <span data-ttu-id="c9cae-264">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="c9cae-264">**Report spam**</span></span>

![Параметры на кнопке Действие](../../media/user-submission-custom-mailbox-action-button.png)
