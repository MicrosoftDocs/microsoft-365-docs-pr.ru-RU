---
title: Отправки администратором
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать портал отправки в центре безопасности & соответствия требованиям для отправки подозрительных сообщений электронной почты, подозрительных сообщений фишинга, спама и других потенциально опасных сообщений, URL-адресов и файлов в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726849"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="ed5e0-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed5e0-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="ed5e0-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут использовать портал отправки в центре безопасности & соответствия требованиям для отправки электронных сообщений, URL-адресов и вложений в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="ed5e0-105">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="ed5e0-106">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="ed5e0-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ed5e0-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ed5e0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ed5e0-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ed5e0-110">Чтобы перейти непосредственно на страницу **отправки** , используйте <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="ed5e0-111">Прежде чем выполнять процедуры, описанные в этом разделе, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="ed5e0-112">Чтобы передать сообщения и файлы в корпорацию Майкрософт, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ed5e0-113">**Управление организацией** или **администратор безопасности** в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ed5e0-114">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ed5e0-115">Для доступа только для чтения к порталу отправки необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ed5e0-116">**Средство чтения безопасности** в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ed5e0-117">**Управление организацией только с просмотром** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="ed5e0-118">Для получения дополнительных сведений о том, как пользователи могут отсылать сообщения и файлы в корпорацию Майкрософт, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="ed5e0-119">Сообщить о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed5e0-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="ed5e0-120">В центре безопасности & соответствия требованиям перейдите к разделу **Управление угрозами** \> **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="ed5e0-121">На открывшейся **странице "отправки"** нажмите кнопку **создать** .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="ed5e0-122">Используйте всплывающее всплывающее окно **отправки** , которое появляется для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="ed5e0-123">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed5e0-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="ed5e0-124">В разделе **тип объекта** выберите **Электронная почта**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="ed5e0-125">В разделе **формат отправки** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="ed5e0-126">**Идентификатор сетевого сообщения**: это значение GUID, которое доступно в заголовке **X-MS-Exchange-Organization-Network-Message-ID** в сообщении.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="ed5e0-127">**Файл**: нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="ed5e0-128">В открывшемся диалоговом окне найдите и выберите файл. EML или. MSG, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="ed5e0-129">В разделе **получатели** укажите одного или нескольких получателей, для которых необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="ed5e0-130">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="ed5e0-131">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ed5e0-132">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ed5e0-133">**Должны быть заблокированы**: выберите **спам**, **Фишинг**или **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="ed5e0-134">Если вы не уверены, используйте свои лучшие решения.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="ed5e0-135">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="ed5e0-136">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="ed5e0-137">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="ed5e0-138">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="ed5e0-139">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="ed5e0-140">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="ed5e0-140">When you're finished, click the **Submit** button.</span></span>

![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="ed5e0-142">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed5e0-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="ed5e0-143">В разделе **тип объекта** выберите **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="ed5e0-144">В появившемся поле введите полный URL-адрес (например, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="ed5e0-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="ed5e0-145">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ed5e0-146">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ed5e0-147">**Должны быть заблокированы**: выберите **Фишинг** или **вредоносную**программу.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="ed5e0-148">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="ed5e0-148">When you're finished, click the **Submit** button.</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="ed5e0-150">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed5e0-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="ed5e0-151">В разделе **тип объекта** выберите **вложение**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="ed5e0-152">Нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-152">Click **Choose File**.</span></span> <span data-ttu-id="ed5e0-153">В открывшемся диалоговом окне найдите и выберите файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="ed5e0-154">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ed5e0-155">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ed5e0-156">**Должны быть заблокированы**: **единственным** выбором и автоматически выбрано значение...</span><span class="sxs-lookup"><span data-stu-id="ed5e0-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="ed5e0-157">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="ed5e0-157">When you're finished, click the **Submit** button.</span></span>

![Пример отправки вложений](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="ed5e0-159">Просмотр отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="ed5e0-159">View admin submissions</span></span>

1. <span data-ttu-id="ed5e0-160">В центре безопасности & соответствия требованиям перейдите к разделу **Управление угрозами** \> **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="ed5e0-161">На появившейся странице **отправки** убедитесь, что выбрана вкладка " **отправленные администратором** ".</span><span class="sxs-lookup"><span data-stu-id="ed5e0-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="ed5e0-162">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **идентификатору отправки** , указав значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ed5e0-163">Update</span><span class="sxs-lookup"><span data-stu-id="ed5e0-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ed5e0-164">Чтобы изменить условия фильтра, нажмите кнопку " **идентификатор отправки** " и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="ed5e0-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-165">**Sender**</span></span>
- <span data-ttu-id="ed5e0-166">**Тема/URL-адрес/имя файла**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="ed5e0-167">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-167">**Submitted by**</span></span>
- <span data-ttu-id="ed5e0-168">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-168">**Submission type**</span></span>
- <span data-ttu-id="ed5e0-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-169">**Status**</span></span>

![Параметры фильтра для отправки администратором](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="ed5e0-171">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ed5e0-172">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="ed5e0-173">Под диаграммой расположены три вкладки: **Электронная почта** (по умолчанию), **URL-адрес**и **вложение**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="ed5e0-174">Просмотр отправляемых по электронной почте сообщений администратора</span><span class="sxs-lookup"><span data-stu-id="ed5e0-174">View admin email submissions</span></span>

<span data-ttu-id="ed5e0-175">Перейдите на вкладку **Электронная почта** .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-175">Click the **Email** tab.</span></span>

<span data-ttu-id="ed5e0-176">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ed5e0-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-177">**Date**</span></span>
- <span data-ttu-id="ed5e0-178">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-178">**Submission ID**</span></span>
- <span data-ttu-id="ed5e0-179">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-180">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-181">**Sender**</span></span>
- <span data-ttu-id="ed5e0-182">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-183">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-183">**Submission type**</span></span>
- <span data-ttu-id="ed5e0-184">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-184">**Delivery reason**</span></span>
- <span data-ttu-id="ed5e0-185">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-186">**Тип элемента управления**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-186">**Control type**</span></span>
- <span data-ttu-id="ed5e0-187">**Источник элемента управления**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-187">**Control source**</span></span>

  <span data-ttu-id="ed5e0-188"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="ed5e0-189">Просмотр отправок URL-адреса администратора</span><span class="sxs-lookup"><span data-stu-id="ed5e0-189">View admin URL submissions</span></span>

<span data-ttu-id="ed5e0-190">Перейдите на вкладку **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-190">Click the **URL** tab.</span></span>

<span data-ttu-id="ed5e0-191">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ed5e0-192">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-192">**Date**</span></span>
- <span data-ttu-id="ed5e0-193">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-193">**Submission ID**</span></span>
- <span data-ttu-id="ed5e0-194">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-196">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-196">**Submission type**</span></span>
- <span data-ttu-id="ed5e0-197">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ed5e0-198"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="ed5e0-199">Просмотр отправки вложений администратора</span><span class="sxs-lookup"><span data-stu-id="ed5e0-199">View admin attachment submissions</span></span>

<span data-ttu-id="ed5e0-200">Перейдите на вкладку **вложения** .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="ed5e0-201">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ed5e0-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-202">**Date**</span></span>
- <span data-ttu-id="ed5e0-203">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-203">**Submission ID**</span></span>
- <span data-ttu-id="ed5e0-204">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-205">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-206">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-206">**Submission type**</span></span>
- <span data-ttu-id="ed5e0-207">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ed5e0-208"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="ed5e0-209">Просмотр отправленных пользователем данных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ed5e0-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="ed5e0-210">Если вы развернули [надстройку "сообщение отчета](enable-the-report-message-add-in.md)" или используете [встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), вы можете увидеть, какие пользователи будут создавать отчеты на вкладке " **Отправленные пользователем** ".</span><span class="sxs-lookup"><span data-stu-id="ed5e0-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="ed5e0-211">В центре безопасности & соответствия требованиям перейдите к разделу **Управление угрозами** \> **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="ed5e0-212">На появившейся странице **отправки** перейдите на вкладку " **Отправленные пользователем** ".</span><span class="sxs-lookup"><span data-stu-id="ed5e0-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="ed5e0-213">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ed5e0-214">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-214">**Submitted on**</span></span>
- <span data-ttu-id="ed5e0-215">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-216">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-217">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-217">**Sender**</span></span>
- <span data-ttu-id="ed5e0-218">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-219">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-219">**Submission type**</span></span>

<span data-ttu-id="ed5e0-220"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="ed5e0-221">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **отправителю** , указав значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ed5e0-222">Update</span><span class="sxs-lookup"><span data-stu-id="ed5e0-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ed5e0-223">Чтобы изменить условия фильтра, нажмите кнопку **отправитель** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="ed5e0-224">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-224">**Sender domain**</span></span>
- <span data-ttu-id="ed5e0-225">**Тема**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-225">**Subject**</span></span>
- <span data-ttu-id="ed5e0-226">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-226">**Submitted by**</span></span>
- <span data-ttu-id="ed5e0-227">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-227">**Submission type**</span></span>
- <span data-ttu-id="ed5e0-228">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-228">**Sender IP**</span></span>

![Параметры фильтра для отправки пользователя](../../media/user-submissions-filter-options.png)

<span data-ttu-id="ed5e0-230">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ed5e0-231">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="ed5e0-232">Просмотр отправленных пользователем данных в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="ed5e0-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="ed5e0-233">Если вы [настроили настраиваемый почтовый ящик](user-submission.md) для получения сообщений, отправленных пользователями, вы можете просматривать и отправлять сообщения, которые были доставлены в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="ed5e0-234">В центре безопасности & соответствия требованиям перейдите к разделу **Управление угрозами** \> **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="ed5e0-235">На появившейся странице **отправки** щелкните вкладку **настраиваемый почтовый ящик** .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="ed5e0-236">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ed5e0-237">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-237">**Submitted on**</span></span>
- <span data-ttu-id="ed5e0-238">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-239">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-240">**Sender**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-240">**Sender**</span></span>
- <span data-ttu-id="ed5e0-241">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ed5e0-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ed5e0-242">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-242">**Submission type**</span></span>

<span data-ttu-id="ed5e0-243">В верхней части страницы вы можете ввести дату начала, дату окончания, а затем отфильтровать **их, указав** значение в поле и нажав ![ кнопку обновить ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="ed5e0-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ed5e0-244">Update</span><span class="sxs-lookup"><span data-stu-id="ed5e0-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ed5e0-245">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ed5e0-246">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="ed5e0-247">Передача сообщений в корпорацию Майкрософт из настраиваемого почтового ящика</span><span class="sxs-lookup"><span data-stu-id="ed5e0-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="ed5e0-248">Если вы настроили личный почтовый ящик для перехвата сообщений, отправленных пользователями, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="ed5e0-249">Это позволяет эффективно переместить пользователя в отправку администратором.</span><span class="sxs-lookup"><span data-stu-id="ed5e0-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="ed5e0-250">На вкладке **настраиваемый почтовый ящик** выберите в списке нужное сообщение, нажмите кнопку **действия** и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ed5e0-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="ed5e0-251">**Очистка отчета**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-251">**Report clean**</span></span>
- <span data-ttu-id="ed5e0-252">**Фишинг отчетов**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-252">**Report phishing**</span></span>
- <span data-ttu-id="ed5e0-253">**Отправка отчетов о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-253">**Report malware**</span></span>
- <span data-ttu-id="ed5e0-254">**Отправка отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="ed5e0-254">**Report spam**</span></span>

![Параметры на кнопке действие](../../media/user-submission-custom-mailbox-action-button.png)
