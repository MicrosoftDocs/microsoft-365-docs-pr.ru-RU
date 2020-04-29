---
title: Отправки, отправки, проблемы с нежелательной почтой администраторами, false (неотрицательные), отправить фишинг, отправлять электронную почту для сканирования, подозрительные сообщения электронной почты в Office 365, сканировать почту, сканировать почту, отправлять сообщения электронной почты, отправлять сообщения электронной почты, сообщения электронной почты, подозрительные сообщения, подозрительные сообщения электронной почты в корпорацию Майкрософт, сообщать о мошеннических сообщениях в корпорацию Майкрософт. , отчитываться о вредоносных сообщениях в Майкрософт, спаме в папке "Входящие", вирусы в электронной почте
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
description: Сведения о том, как отправлять подозрительные сообщения электронной почты, подозрительные фишинговые сообщения, спам и другие потенциально опасные сообщения, URL-адреса и файлы из компании в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: 73c33ba1218a710c33f8b2675bc65c0a7486efda
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921532"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b9959-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9959-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="b9959-104">Если вы являетесь администратором в организации Microsoft 365 с почтовыми ящиками в Exchange Online, вы можете использовать портал отправки в центре безопасности & соответствия требованиям, чтобы отправлять сообщения электронной почты, URL-адреса и вложения в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="b9959-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b9959-105">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="b9959-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="b9959-106">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="b9959-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="b9959-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b9959-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b9959-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b9959-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b9959-109">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b9959-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b9959-110">Чтобы перейти непосредственно на страницу **отправки** , используйте <https://protection.office.com/reportsubmission>.</span><span class="sxs-lookup"><span data-stu-id="b9959-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="b9959-111">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="b9959-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="b9959-112">Для добавления, изменения и удаления политик защиты от нежелательной почты необходимо быть участником группы ролей " **Управление организацией**", " **администратор безопасности**" или " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="b9959-113">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b9959-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b9959-114">Для получения дополнительных сведений о том, как пользователи могут отсылать сообщения и файлы в корпорацию Майкрософт, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b9959-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="b9959-115">Сообщить о подозрительном содержимом в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9959-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="b9959-116">В центре безопасности & соответствия требованиям перейдите к разделу \> **Управление угрозами** **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="b9959-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b9959-117">На открывшейся **странице "отправки"** нажмите кнопку **создать** .</span><span class="sxs-lookup"><span data-stu-id="b9959-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="b9959-118">Используйте всплывающее всплывающее окно **отправки** , которое появляется для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b9959-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b9959-119">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9959-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="b9959-120">В разделе **тип объекта** выберите **Электронная почта**.</span><span class="sxs-lookup"><span data-stu-id="b9959-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="b9959-121">В разделе **формат отправки** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b9959-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="b9959-122">**Идентификатор сетевого сообщения**: это значение GUID, которое доступно в заголовке **X-MS-Exchange-Organization-Network-Message-ID** в сообщении.</span><span class="sxs-lookup"><span data-stu-id="b9959-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="b9959-123">**Файл**: нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="b9959-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="b9959-124">В открывшемся диалоговом окне найдите и выберите файл. EML или. MSG, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="b9959-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="b9959-125">В разделе **получатели** укажите одного или нескольких получателей, для которых необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="b9959-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="b9959-126">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="b9959-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="b9959-127">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b9959-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b9959-128">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="b9959-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b9959-129">**Должны быть заблокированы**: выберите **спам**, **Фишинг**или **вредоносная программа**.</span><span class="sxs-lookup"><span data-stu-id="b9959-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="b9959-130">Если вы не уверены, используйте свои лучшие решения.</span><span class="sxs-lookup"><span data-stu-id="b9959-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="b9959-131">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="b9959-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="b9959-132">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="b9959-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="b9959-133">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="b9959-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="b9959-134">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="b9959-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="b9959-135">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="b9959-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="b9959-136">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-136">When you're finished, click the **Submit** button.</span></span>

![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b9959-138">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9959-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="b9959-139">В разделе **тип объекта** выберите **URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="b9959-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="b9959-140">В появившемся поле введите полный URL-адрес (например, <https://www.fabrikam.com/marketing.html>).</span><span class="sxs-lookup"><span data-stu-id="b9959-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="b9959-141">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b9959-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b9959-142">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="b9959-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b9959-143">**Должны быть заблокированы**: выберите **Фишинг** или **вредоносную**программу.</span><span class="sxs-lookup"><span data-stu-id="b9959-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="b9959-144">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-144">When you're finished, click the **Submit** button.</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="b9959-146">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9959-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="b9959-147">В разделе **тип объекта** выберите **вложение**.</span><span class="sxs-lookup"><span data-stu-id="b9959-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="b9959-148">Нажмите кнопку **выбрать файл**.</span><span class="sxs-lookup"><span data-stu-id="b9959-148">Click **Choose File**.</span></span> <span data-ttu-id="b9959-149">В открывшемся диалоговом окне найдите и выберите файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="b9959-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="b9959-150">В разделе **Причина отправки** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b9959-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b9959-151">**Не должны быть заблокированы**</span><span class="sxs-lookup"><span data-stu-id="b9959-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b9959-152">**Должны быть заблокированы**: **единственным** выбором и автоматически выбрано значение...</span><span class="sxs-lookup"><span data-stu-id="b9959-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="b9959-153">По завершении нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-153">When you're finished, click the **Submit** button.</span></span>

![Пример отправки вложений](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="b9959-155">Просмотр отправленных администратором сообщений</span><span class="sxs-lookup"><span data-stu-id="b9959-155">View admin submissions</span></span>

1. <span data-ttu-id="b9959-156">В центре безопасности & соответствия требованиям перейдите к разделу \> **Управление угрозами** **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="b9959-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b9959-157">На появившейся странице **отправки** убедитесь, что выбрана вкладка " **отправленные администратором** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="b9959-158">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **идентификатору отправки** , указав значение в поле и нажав ![кнопку](../../media/scc-quarantine-refresh.png)обновить.</span><span class="sxs-lookup"><span data-stu-id="b9959-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b9959-159">Update</span><span class="sxs-lookup"><span data-stu-id="b9959-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b9959-160">Чтобы изменить условия фильтра, нажмите кнопку " **идентификатор отправки** " и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b9959-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="b9959-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9959-161">**Sender**</span></span>
- <span data-ttu-id="b9959-162">**Тема/URL-адрес/имя файла**</span><span class="sxs-lookup"><span data-stu-id="b9959-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="b9959-163">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="b9959-163">**Submitted by**</span></span>
- <span data-ttu-id="b9959-164">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-164">**Submission type**</span></span>
- <span data-ttu-id="b9959-165">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="b9959-165">**Status**</span></span>

![Параметры фильтра для отправки администратором](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="b9959-167">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="b9959-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b9959-168">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="b9959-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="b9959-169">Под диаграммой расположены три вкладки: **Электронная почта** (по умолчанию), **URL-адрес**и **вложение**.</span><span class="sxs-lookup"><span data-stu-id="b9959-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="b9959-170">Просмотр отправляемых по электронной почте сообщений администратора</span><span class="sxs-lookup"><span data-stu-id="b9959-170">View admin email submissions</span></span>

<span data-ttu-id="b9959-171">Перейдите на вкладку **Электронная почта** .</span><span class="sxs-lookup"><span data-stu-id="b9959-171">Click the **Email** tab.</span></span>

<span data-ttu-id="b9959-172">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="b9959-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b9959-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="b9959-173">**Date**</span></span>
- <span data-ttu-id="b9959-174">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-174">**Submission ID**</span></span>
- <span data-ttu-id="b9959-175">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-176">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9959-177">**Sender**</span></span>
- <span data-ttu-id="b9959-178">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-179">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-179">**Submission type**</span></span>
- <span data-ttu-id="b9959-180">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="b9959-180">**Delivery reason**</span></span>
- <span data-ttu-id="b9959-181">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-182">**Тип элемента управления**</span><span class="sxs-lookup"><span data-stu-id="b9959-182">**Control type**</span></span>
- <span data-ttu-id="b9959-183">**Источник элемента управления**</span><span class="sxs-lookup"><span data-stu-id="b9959-183">**Control source**</span></span>

  <span data-ttu-id="b9959-184"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="b9959-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="b9959-185">Просмотр отправок URL-адреса администратора</span><span class="sxs-lookup"><span data-stu-id="b9959-185">View admin URL submissions</span></span>

<span data-ttu-id="b9959-186">Перейдите на вкладку **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="b9959-186">Click the **URL** tab.</span></span>

<span data-ttu-id="b9959-187">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="b9959-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b9959-188">**Date**</span><span class="sxs-lookup"><span data-stu-id="b9959-188">**Date**</span></span>
- <span data-ttu-id="b9959-189">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-189">**Submission ID**</span></span>
- <span data-ttu-id="b9959-190">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-192">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-192">**Submission type**</span></span>
- <span data-ttu-id="b9959-193">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b9959-194"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="b9959-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="b9959-195">Просмотр отправки вложений администратора</span><span class="sxs-lookup"><span data-stu-id="b9959-195">View admin attachment submissions</span></span>

<span data-ttu-id="b9959-196">Перейдите на вкладку **вложения** .</span><span class="sxs-lookup"><span data-stu-id="b9959-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="b9959-197">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="b9959-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b9959-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="b9959-198">**Date**</span></span>
- <span data-ttu-id="b9959-199">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-199">**Submission ID**</span></span>
- <span data-ttu-id="b9959-200">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-201">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-202">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-202">**Submission type**</span></span>
- <span data-ttu-id="b9959-203">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b9959-204"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="b9959-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="b9959-205">Просмотр отправленных пользователем данных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b9959-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="b9959-206">Если вы развернули [надстройку "сообщение отчета](enable-the-report-message-add-in.md)" или используете [встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), вы можете увидеть, какие пользователи будут создавать отчеты на вкладке " **Отправленные пользователем** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="b9959-207">В центре безопасности & соответствия требованиям перейдите к разделу \> **Управление угрозами** **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="b9959-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b9959-208">На появившейся странице **отправки** перейдите на вкладку " **Отправленные пользователем** ".</span><span class="sxs-lookup"><span data-stu-id="b9959-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="b9959-209">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="b9959-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b9959-210">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="b9959-210">**Submitted on**</span></span>
- <span data-ttu-id="b9959-211">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-212">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9959-213">**Sender**</span></span>
- <span data-ttu-id="b9959-214">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-215">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-215">**Submission type**</span></span>

<span data-ttu-id="b9959-216"><sup>\*</sup>Если щелкнуть это значение, в всплывающем меню будет отображаться подробная информация.</span><span class="sxs-lookup"><span data-stu-id="b9959-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="b9959-217">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) фильтровать по **отправителю** , указав значение в поле и нажав ![кнопку](../../media/scc-quarantine-refresh.png)обновить.</span><span class="sxs-lookup"><span data-stu-id="b9959-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b9959-218">Update</span><span class="sxs-lookup"><span data-stu-id="b9959-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b9959-219">Чтобы изменить условия фильтра, нажмите кнопку **отправитель** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="b9959-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="b9959-220">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="b9959-220">**Sender domain**</span></span>
- <span data-ttu-id="b9959-221">**Тема**</span><span class="sxs-lookup"><span data-stu-id="b9959-221">**Subject**</span></span>
- <span data-ttu-id="b9959-222">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="b9959-222">**Submitted by**</span></span>
- <span data-ttu-id="b9959-223">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-223">**Submission type**</span></span>
- <span data-ttu-id="b9959-224">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="b9959-224">**Sender IP**</span></span>

![Параметры фильтра для отправки пользователя](../../media/user-submissions-filter-options.png)

<span data-ttu-id="b9959-226">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="b9959-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b9959-227">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="b9959-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="b9959-228">Просмотр отправленных пользователем данных в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="b9959-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="b9959-229">Если вы [настроили настраиваемый почтовый ящик](user-submission.md) для получения сообщений, отправленных пользователями, вы можете просматривать и отправлять сообщения, которые были доставлены в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9959-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="b9959-230">В центре безопасности & соответствия требованиям перейдите к разделу \> **Управление угрозами** **Обзор** \> **сообщений для отправки администратором**.</span><span class="sxs-lookup"><span data-stu-id="b9959-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="b9959-231">На появившейся странице **отправки** щелкните вкладку **настраиваемый почтовый ящик** .</span><span class="sxs-lookup"><span data-stu-id="b9959-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="b9959-232">Можно нажать кнопку **Параметры столбца** в нижней части страницы, чтобы добавить или удалить столбцы из представления:</span><span class="sxs-lookup"><span data-stu-id="b9959-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b9959-233">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="b9959-233">**Submitted on**</span></span>
- <span data-ttu-id="b9959-234">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-235">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9959-236">**Sender**</span></span>
- <span data-ttu-id="b9959-237">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9959-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b9959-238">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="b9959-238">**Submission type**</span></span>

<span data-ttu-id="b9959-239">В верхней части страницы вы можете ввести дату начала, дату окончания, а затем отфильтровать **их, указав** значение в поле и нажав ![кнопку](../../media/scc-quarantine-refresh.png)обновить.</span><span class="sxs-lookup"><span data-stu-id="b9959-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b9959-240">Update</span><span class="sxs-lookup"><span data-stu-id="b9959-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b9959-241">Чтобы экспортировать результаты, нажмите кнопку **Экспорт** в верхней части страницы, а затем выберите **данные диаграммы** или **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="b9959-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b9959-242">В появившемся диалоговом окне сохраните CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="b9959-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="b9959-243">Передача сообщений в корпорацию Майкрософт из настраиваемого почтового ящика</span><span class="sxs-lookup"><span data-stu-id="b9959-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="b9959-244">Если вы настроили личный почтовый ящик для перехвата сообщений, отправленных пользователями, без отправки сообщений в корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="b9959-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="b9959-245">Это позволяет эффективно переместить пользователя в отправку администратором.</span><span class="sxs-lookup"><span data-stu-id="b9959-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="b9959-246">На вкладке **настраиваемый почтовый ящик** выберите в списке нужное сообщение, нажмите кнопку **действия** и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="b9959-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="b9959-247">**Очистка отчета**</span><span class="sxs-lookup"><span data-stu-id="b9959-247">**Report clean**</span></span>
- <span data-ttu-id="b9959-248">**Фишинг отчетов**</span><span class="sxs-lookup"><span data-stu-id="b9959-248">**Report phishing**</span></span>
- <span data-ttu-id="b9959-249">**Отправка отчетов о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="b9959-249">**Report malware**</span></span>
- <span data-ttu-id="b9959-250">**Отправка отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="b9959-250">**Report spam**</span></span>

![Параметры на кнопке действие](../../media/user-submission-custom-mailbox-action-button.png)
