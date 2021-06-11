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
description: Администраторы могут узнать, как использовать портал Отправки в центре безопасности Microsoft 365 для отправки подозрительных сообщений электронной почты, подозрительных фишинговых сообщений, нежелательной почты и других потенциально вредных сообщений, URL-адресов и вложений электронной почты в Корпорацию Майкрософт для повторного использования.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878692"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="37e88-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37e88-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37e88-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="37e88-104">**Applies to**</span></span>
- [<span data-ttu-id="37e88-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="37e88-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="37e88-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="37e88-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="37e88-107">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online администраторы могут использовать портал Отправки в Центре соответствия требованиям & безопасности для отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="37e88-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="37e88-108">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="37e88-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="37e88-109">**Проверка подлинности электронной** почты. Сведения о том, прошла ли проверка подлинности электронной почты при ее доставке или сбой.</span><span class="sxs-lookup"><span data-stu-id="37e88-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="37e88-110">**Хиты** политики. Сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиента, переопределив наши решения фильтра службы.</span><span class="sxs-lookup"><span data-stu-id="37e88-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="37e88-111">**Репутация и детонация полезной** нагрузки: проверка url-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="37e88-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="37e88-112">**Анализ грейдера.** Проверка, сделанная грейдерами,чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="37e88-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37e88-113">Анализ репутации/детонации и грейдера полезной нагрузки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="37e88-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="37e88-114">Сведения не могут выходить за пределы организации, если данные не должны покидать границу клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="37e88-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="37e88-115">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт см. в этой ссылке. [](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="37e88-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37e88-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="37e88-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37e88-117">Вы открываете центр Microsoft 365 безопасности по <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="37e88-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="37e88-118">Чтобы перейти непосредственно на **страницу Отправки,** используйте <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="37e88-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="37e88-119">Чтобы отправить сообщения и файлы в Корпорацию Майкрософт, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="37e88-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="37e88-120">**Управление организацией** или **чтение** безопасности [в центре Microsoft 365 безопасности.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="37e88-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="37e88-121">**Управление организацией** [в Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="37e88-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="37e88-122">Обратите внимание, что членство в [](#view-user-submissions-to-the-custom-mailbox) этой группе ролей необходимо для просмотра пользовательских представлений в настраиваемом почтовом ящике, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="37e88-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="37e88-123">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в Корпорацию Майкрософт, см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="37e88-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="37e88-124">Сообщение о подозрительном контенте в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37e88-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="37e88-125">В центре [Microsoft 365](../defender/overview-security-center.md)безопасности перейдите  к отправкам и убедитесь, что вы на вкладке Отправка для анализа, а затем нажмите кнопку Отправить в **Microsoft для проверки**. </span><span class="sxs-lookup"><span data-stu-id="37e88-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="37e88-126">Используйте **отправку в Корпорацию Майкрософт** для проверки вылетов, которые, как представляется, представляют сообщение, URL-адрес или вложение электронной почты, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="37e88-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="37e88-127">Отправка сомнительного сообщения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37e88-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="37e88-128">В разделе **Выбор типа отправки** выберите электронную **почту.**</span><span class="sxs-lookup"><span data-stu-id="37e88-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="37e88-129">В разделе **Добавление сетевого сообщения или** отправка раздела файл электронной почты используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="37e88-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="37e88-130">Добавьте сетевой **ID** сообщения электронной почты. Это значение GUID, доступное в загонщике **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **загоне X-MS-Office365-Filtering-Correlation-Id** в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="37e88-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="37e88-131">**Upload файла электронной почты:** Нажмите **кнопку Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="37e88-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="37e88-132">В открываемом диалоговом окте найти и выбрать файл .eml или .msg, а затем нажмите **кнопку Открыть**.</span><span class="sxs-lookup"><span data-stu-id="37e88-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="37e88-133">Возможность отправки сообщений в течение 30 дней была временно приостановлена для defender для Office 365 клиентов.</span><span class="sxs-lookup"><span data-stu-id="37e88-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="37e88-134">Администраторы смогут возвращаться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="37e88-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="37e88-135">В разделе **Выбор получателя,** у которого была проблема, укажите получателя, против которого необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="37e88-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="37e88-136">Проверка политики определяет, не обходится ли проверка электронной почты из-за политики пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="37e88-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="37e88-137">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="37e88-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="37e88-138">**Не должно было быть заблокировано**</span><span class="sxs-lookup"><span data-stu-id="37e88-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="37e88-139">**Должны были быть заблокированы:** Выберите **спам,** **фишинг** или **вредоносные программы**.</span><span class="sxs-lookup"><span data-stu-id="37e88-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="37e88-140">Если вы не уверены, используйте свои лучшие суждения.</span><span class="sxs-lookup"><span data-stu-id="37e88-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="37e88-141">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="37e88-141">When you're finished, click the **Submit** button.</span></span>

   ![Новый пример отправки URL-адресов](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="37e88-143">Отправка подозрительного URL-адреса в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37e88-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="37e88-144">В разделе **Выберите тип отправки** выберите **URL-адрес.**</span><span class="sxs-lookup"><span data-stu-id="37e88-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="37e88-145">В поле, которое отображается, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="37e88-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="37e88-146">В разделе **Причина отправки** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="37e88-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="37e88-147">**Не должно было быть заблокировано**</span><span class="sxs-lookup"><span data-stu-id="37e88-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="37e88-148">**Должны были быть заблокированы:** Выберите **фишинг** или **вредоносные программы**.</span><span class="sxs-lookup"><span data-stu-id="37e88-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="37e88-149">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="37e88-149">When you're finished, click the **Submit** button.</span></span>

   ![Новый пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="37e88-151">Отправка предполагаемого вложения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37e88-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="37e88-152">В разделе **Выбор типа отправки** выберите вложение **электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="37e88-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="37e88-153">Нажмите **кнопку Выберите файл**.</span><span class="sxs-lookup"><span data-stu-id="37e88-153">Click **Choose File**.</span></span> <span data-ttu-id="37e88-154">В открываемом диалоговом окте найти и выбрать файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="37e88-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="37e88-155">В разделе **Причина отправки** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="37e88-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="37e88-156">**Не должно было быть заблокировано**</span><span class="sxs-lookup"><span data-stu-id="37e88-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="37e88-157">**Должны были быть заблокированы:** **вредоносные** программы является единственным выбором, и автоматически выбирается.</span><span class="sxs-lookup"><span data-stu-id="37e88-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="37e88-158">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="37e88-158">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки вложения](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="37e88-160">Просмотр элементов, отправленных для анализа</span><span class="sxs-lookup"><span data-stu-id="37e88-160">View items Submitted for analysis</span></span>

<span data-ttu-id="37e88-161">В центре Microsoft 365 безопасности перейдите к **отправкам** и убедитесь, что вы на вкладке **Отправка для анализа**</span><span class="sxs-lookup"><span data-stu-id="37e88-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="37e88-162">В панели команд в середине страницы можно ввести дату начала, дату окончания, а (по умолчанию) можно отфильтровать по представлению **ID** (значение GUID, назначенное каждой отправке), введите значение в поле и нажав кнопку ![ Обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="37e88-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="37e88-163">Update</span><span class="sxs-lookup"><span data-stu-id="37e88-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="37e88-164">Чтобы изменить критерии фильтрации, нажмите кнопку **Фильтр** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="37e88-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="37e88-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="37e88-165">**Sender**</span></span>
- <span data-ttu-id="37e88-166">**Имя subject/URL/File**</span><span class="sxs-lookup"><span data-stu-id="37e88-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="37e88-167">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="37e88-167">**Submitted by**</span></span>
- <span data-ttu-id="37e88-168">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-168">**Submission type**</span></span>
- <span data-ttu-id="37e88-169">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="37e88-169">**Status**</span></span>

![Новые параметры фильтра для отправки администратора](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="37e88-171">Чтобы экспортировать результаты, щелкните **Экспорт** в верхней части страницы и выберите **диаграммы данных** или **таблицы**.</span><span class="sxs-lookup"><span data-stu-id="37e88-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="37e88-172">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="37e88-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="37e88-173">На графике приведены три вкладки: **электронная** почта (по умолчанию), **URL-адрес** и **вложение электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="37e88-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="37e88-174">Просмотр сообщений электронной почты администратора</span><span class="sxs-lookup"><span data-stu-id="37e88-174">View admin email submissions</span></span>

<span data-ttu-id="37e88-175">Вы можете нажать кнопку **Настройка столбцов** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="37e88-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="37e88-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="37e88-176">**Date**</span></span>
- <span data-ttu-id="37e88-177">**ID отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="37e88-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="37e88-178">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-179">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-180">**Sender**</span><span class="sxs-lookup"><span data-stu-id="37e88-180">**Sender**</span></span>
- <span data-ttu-id="37e88-181">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-182">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-182">**Submission type**</span></span>
- <span data-ttu-id="37e88-183">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="37e88-183">**Delivery reason**</span></span>
- <span data-ttu-id="37e88-184">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="37e88-185"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="37e88-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="37e88-186">Сведения о повторном представлении администратора</span><span class="sxs-lookup"><span data-stu-id="37e88-186">Admin submission rescan details</span></span>

<span data-ttu-id="37e88-187">Сообщения, отправленные в представлениях администратора, rescanned и результаты, показанные в вылете детализации представлений:</span><span class="sxs-lookup"><span data-stu-id="37e88-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="37e88-188">Возникновение сбоя при проверке подлинности электронной почты отправителя в момент доставки.</span><span class="sxs-lookup"><span data-stu-id="37e88-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="37e88-189">Сведения о любых совпадениях политик, которые могут повлиять на решение по безопасности касательно сообщения или переопределить его.</span><span class="sxs-lookup"><span data-stu-id="37e88-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="37e88-190">Текущие результаты отключения, чтобы определить, были ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными или нет.</span><span class="sxs-lookup"><span data-stu-id="37e88-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="37e88-191">Отзывы от грейдеров.</span><span class="sxs-lookup"><span data-stu-id="37e88-191">Feedback from graders.</span></span>

<span data-ttu-id="37e88-192">Если было обнаружено переопределение, повторное сканирование должно завершиться через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="37e88-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="37e88-193">Если в проверке подлинности или доставке электронной почты не возникло проблем с переопределением, то отзывы от грейдеров могут занять до одного дня.</span><span class="sxs-lookup"><span data-stu-id="37e88-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="37e88-194">Просмотр url-адресов администратора</span><span class="sxs-lookup"><span data-stu-id="37e88-194">View admin URL submissions</span></span>

<span data-ttu-id="37e88-195">Щелкните **вкладку** URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="37e88-195">Click the **URL** tab.</span></span>

<span data-ttu-id="37e88-196">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="37e88-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="37e88-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="37e88-197">**Date**</span></span>
- <span data-ttu-id="37e88-198">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-198">**Submission ID**</span></span>
- <span data-ttu-id="37e88-199">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-201">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-201">**Submission type**</span></span>
- <span data-ttu-id="37e88-202">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="37e88-203"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="37e88-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="37e88-204">Просмотр отправки вложений электронной почты</span><span class="sxs-lookup"><span data-stu-id="37e88-204">View email attachment submissions</span></span>

<span data-ttu-id="37e88-205">Щелкните **вкладку Вложения.**</span><span class="sxs-lookup"><span data-stu-id="37e88-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="37e88-206">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="37e88-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="37e88-207">**Date**</span><span class="sxs-lookup"><span data-stu-id="37e88-207">**Date**</span></span>
- <span data-ttu-id="37e88-208">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-208">**Submission ID**</span></span>
- <span data-ttu-id="37e88-209">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-210">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-211">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-211">**Submission type**</span></span>
- <span data-ttu-id="37e88-212">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="37e88-213"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="37e88-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="37e88-214">Просмотр пользовательских представлений в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="37e88-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="37e88-215">Если вы развернули надстройку ["Сообщение](enable-the-report-message-add-in.md)отчетов", надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенную отчетность в Outlook  в [Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие отчеты пользователи сообщают на вкладке Отправки пользователей.</span><span class="sxs-lookup"><span data-stu-id="37e88-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="37e88-216">В Центре & безопасности перейдите в **службу управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="37e88-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="37e88-217">Выберите **вкладку Отправки** пользователя и нажмите кнопку **Новая отправка**.</span><span class="sxs-lookup"><span data-stu-id="37e88-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="37e88-218">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="37e88-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="37e88-219">**Отправлено на**</span><span class="sxs-lookup"><span data-stu-id="37e88-219">**Submitted on**</span></span>
- <span data-ttu-id="37e88-220">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-221">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-222">**Sender**</span><span class="sxs-lookup"><span data-stu-id="37e88-222">**Sender**</span></span>
- <span data-ttu-id="37e88-223">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-224">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-224">**Submission type**</span></span>

<span data-ttu-id="37e88-225"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются в вылете.</span><span class="sxs-lookup"><span data-stu-id="37e88-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="37e88-226">В верхней части страницы можно ввести дату начала, дату окончания и (по  умолчанию) фильтровать отправитель, введите значение в поле и нажав кнопку ![ Обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="37e88-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="37e88-227">Update</span><span class="sxs-lookup"><span data-stu-id="37e88-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="37e88-228">Чтобы изменить критерии фильтрации, нажмите кнопку **Отправитель** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="37e88-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="37e88-229">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="37e88-229">**Sender domain**</span></span>
- <span data-ttu-id="37e88-230">**Тема**</span><span class="sxs-lookup"><span data-stu-id="37e88-230">**Subject**</span></span>
- <span data-ttu-id="37e88-231">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="37e88-231">**Submitted by**</span></span>
- <span data-ttu-id="37e88-232">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-232">**Submission type**</span></span>
- <span data-ttu-id="37e88-233">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="37e88-233">**Sender IP**</span></span>

![Новые параметры фильтра для пользовательских представлений](../../media/user-submissions-filter-options.png)

<span data-ttu-id="37e88-235">Чтобы экспортировать результаты, щелкните **Экспорт** в верхней части страницы и выберите **диаграммы данных** или **таблицы**.</span><span class="sxs-lookup"><span data-stu-id="37e88-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="37e88-236">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="37e88-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="37e88-237">Просмотр пользовательских представлений в настраиваемом почтовом ящике</span><span class="sxs-lookup"><span data-stu-id="37e88-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="37e88-238">**Если** вы [настроили](user-submission.md) настраиваемый почтовый ящик для получения сообщений, сообщаемых пользователем, вы можете просматривать и отправлять сообщения, доставленные в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="37e88-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="37e88-239">В Центре & безопасности перейдите в **службу управления** \> **угрозами.**</span><span class="sxs-lookup"><span data-stu-id="37e88-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="37e88-240">Выберите **вкладку Настраиваемый почтовый ящик.**</span><span class="sxs-lookup"><span data-stu-id="37e88-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="37e88-241">Вы можете нажать **кнопку Параметры Столбец** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="37e88-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="37e88-242">**Отправлено на**</span><span class="sxs-lookup"><span data-stu-id="37e88-242">**Submitted on**</span></span>
- <span data-ttu-id="37e88-243">**Отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-244">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="37e88-245">**Sender**</span></span>
- <span data-ttu-id="37e88-246">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="37e88-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="37e88-247">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="37e88-247">**Submission type**</span></span>

<span data-ttu-id="37e88-248">В верхней части страницы можно ввести дату начала, дату окончания  и отфильтровать ее, введите значение в поле и нажав кнопку ![ ](../../media/scc-quarantine-refresh.png) Обновить.</span><span class="sxs-lookup"><span data-stu-id="37e88-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="37e88-249">Update</span><span class="sxs-lookup"><span data-stu-id="37e88-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="37e88-250">Чтобы экспортировать результаты, щелкните **Экспорт** в верхней части страницы и выберите **диаграммы данных** или **таблицы**.</span><span class="sxs-lookup"><span data-stu-id="37e88-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="37e88-251">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="37e88-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="37e88-252">Если организации настроены на отправку только в настраиваемый почтовый ящик, сообщения не будут отправляться на rescan и результаты на портале сообщений пользователя всегда будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="37e88-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="37e88-253">Отмена отправки пользователей</span><span class="sxs-lookup"><span data-stu-id="37e88-253">Undo user submissions</span></span>

<span data-ttu-id="37e88-254">После отправки подозрительной электронной почты в настраиваемый почтовый ящик у пользователя и администратора нет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="37e88-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="37e88-255">Если пользователь хочет восстановить электронную почту, она будет доступна для восстановления в папках "Удаленные элементы" или "Нежелательной почты".</span><span class="sxs-lookup"><span data-stu-id="37e88-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="37e88-256">Отправка сообщений в Корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="37e88-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="37e88-257">Если настраивается настраиваемый почтовый ящик для перехвата сообщений, сообщаемых пользователями, без отправки сообщений в Корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="37e88-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="37e88-258">Это эффективно перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="37e88-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="37e88-259">На **вкладке Сообщения** пользователя выберите сообщение в списке, нажмите кнопку **Действие** и сделайте один из следующих выборов:</span><span class="sxs-lookup"><span data-stu-id="37e88-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="37e88-260">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="37e88-260">**Report clean**</span></span>
- <span data-ttu-id="37e88-261">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="37e88-261">**Report phishing**</span></span>
- <span data-ttu-id="37e88-262">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="37e88-262">**Report malware**</span></span>
- <span data-ttu-id="37e88-263">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="37e88-263">**Report spam**</span></span>

![Новые параметры на кнопке Действие](../../media/user-submission-custom-mailbox-action-button.png)
