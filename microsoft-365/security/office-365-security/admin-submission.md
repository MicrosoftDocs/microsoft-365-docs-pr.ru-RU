---
title: Отправка администраторами
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
description: Администраторы могут узнать, как отправлять подозрительные сообщения, подозрительные фишинговые сообщения, спам и другие потенциально опасные сообщения, URL-адреса и файлы в корпорацию Майкрософт для сканирования на портале отправки в Центре соответствия требованиям безопасности &.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845970"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d5b2a-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d5b2a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="d5b2a-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online администраторы могут отправлять на сканирование сообщения электронной почты, URL-адреса и вложения в корпорацию Майкрософт на портале отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d5b2a-105">При отправке сообщения вы получите сведения о политиках, которые могли менять входящие сообщения электронной почты в клиенте, а также все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="d5b2a-106">К политикам, в которых может быть разрешена почта, относятся список надежных отправителей отдельного пользователя, а также правила на уровне клиента, например правила потока обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="d5b2a-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="d5b2a-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт см. в [статье "Отчет о сообщениях и файлах" корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d5b2a-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d5b2a-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d5b2a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d5b2a-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d5b2a-110">Чтобы перейти непосредственно на страницу **отправки,** используйте <https://protection.office.com/reportsubmission> этот параметр.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="d5b2a-111">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d5b2a-112">Чтобы отправлять сообщения и файлы в Майкрософт, вам необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d5b2a-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d5b2a-113">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d5b2a-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d5b2a-114">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d5b2a-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d5b2a-115">Для доступа только для чтения к порталу отправки вы должны быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d5b2a-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d5b2a-116">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d5b2a-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d5b2a-117">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d5b2a-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d5b2a-118">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы корпорации Майкрософт, см. в [статье Отчеты о сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d5b2a-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="d5b2a-119">Сообщать майкрософт о подозрительной информации</span><span class="sxs-lookup"><span data-stu-id="d5b2a-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="d5b2a-120">В Центре безопасности & требованиям откройте раздел **"Отправки управления** \> **угрозами",** проверьте, обмениваемся ли вы на **вкладке "Отправки администратором",** а затем нажмите **кнопку "Создать отправку".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="d5b2a-121">Используйте нового всплывающего элемента отправки для отправки сообщения, URL-адреса или вложения, как описано в следующих разделах. **New submission**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d5b2a-122">Отправка английского письма в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d5b2a-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="d5b2a-123">В разделе **"Тип объекта" выберите** "Электронная **почта".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="d5b2a-124">В разделе **"Формат отправки"** используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d5b2a-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="d5b2a-125">**Идентификатор сообщения сети.** Это значение GUID, которое доступно в **заголовке X-MS-Exchange-Organization-Network-Message-Id** сообщения.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="d5b2a-126">**File**: Click **Choose file**.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="d5b2a-127">В открывшемся диалоговом окне найдите и выберите файл EML или MSG, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="d5b2a-128">В разделе **"Получатели"** укажите одного или нескольких получателей, для которых следует запускать проверку политики.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="d5b2a-129">Проверка политикопределяет, прошел ли обход писем в связи с политиками пользователей или организации.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="d5b2a-130">В разделе **"Причина отправки"** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d5b2a-131">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d5b2a-132">**Должно быть заблокировано: "Выбор спама"** или **"Фишинг"** или "Вредоносные **программы".** **Spam**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="d5b2a-133">Если вы не уверены, используйте свою лучшую приглашение.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="d5b2a-134">Если обход фильтра был выполнен из-за политик, которые принадлежат политикам после отправки, вы увидите сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="d5b2a-135">Если не обойти фильтр из-за одной или нескольких политик, проверка будет завершена в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="d5b2a-136">Дополнительные сведения об отправке можно узнать, щелкнув ссылку на ссылку о состоянии.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="d5b2a-137">К ним относятся результаты проверки политики и решение по повторной проверке.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="d5b2a-138">Обратите внимание, что это не запускает электронную почту через стек полной фильтрации Office 365 ATP, но повторно запускает частичное повторное сканирование на основе определенных атрибутов почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="d5b2a-139">По завершении нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-139">When you're finished, click the **Submit** button.</span></span>

![Пример отправки URL-адреса](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d5b2a-141">Отправка подозрительного URL-адреса в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d5b2a-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="d5b2a-142">В разделе **"Типобъекта"** выберите **URL-адрес.**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="d5b2a-143">В появившемся поле введите полный URL-адрес (например, <https://www.fabrikam.com/marketing.html> ).).</span><span class="sxs-lookup"><span data-stu-id="d5b2a-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="d5b2a-144">В разделе **"Причина отправки"** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d5b2a-145">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d5b2a-146">**Должно быть заблокировано: выберите** **"Фишинг" или "Вредоносные** **программы".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="d5b2a-147">По завершении нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-147">When you're finished, click the **Submit** button.</span></span>

![Пример отправки сообщения электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="d5b2a-149">Отправка файла в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d5b2a-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="d5b2a-150">В разделе **"Тип объекта"** выберите **"Вложение".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="d5b2a-151">Щелкните **"Choose File" (Выбрать файл).**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-151">Click **Choose File**.</span></span> <span data-ttu-id="d5b2a-152">В открывшемся диалоговом окне найдите и выберите файл, а затем нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="d5b2a-153">В разделе **"Причина отправки"** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d5b2a-154">**Не следует блокировать**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d5b2a-155">**Должно быть заблокировано:** **"Вредоносное** ПО" выберете не нужно и выбрано автоматически.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="d5b2a-156">По завершении нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-156">When you're finished, click the **Submit** button.</span></span>

![Пример отправки вложений](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="d5b2a-158">Просмотр отправок администраторами</span><span class="sxs-lookup"><span data-stu-id="d5b2a-158">View admin submissions</span></span>

<span data-ttu-id="d5b2a-159">В Центре безопасности & требованиям откройте раздел **"Отправки управления** \> **угрозами",** проверьте, обмениваемся ли вы на **вкладке "Отправки администратором",** а затем нажмите **кнопку "Создать отправку".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="d5b2a-160">В верхней части страницы можно ввести дату начала, дату окончания и (по умолчанию) вы можете отфильтровать по **идентификатору** отправки (значение GUID, назначенное каждому процессу отправки) по средством ввода значения в поле и нажатия ![ кнопки "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="d5b2a-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d5b2a-161">Update</span><span class="sxs-lookup"><span data-stu-id="d5b2a-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d5b2a-162">Чтобы изменить условия фильтра, нажмите кнопку **идентификатор отправки** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d5b2a-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="d5b2a-163">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-163">**Sender**</span></span>
- <span data-ttu-id="d5b2a-164">**Имя субъекта,URL/имя файла**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="d5b2a-165">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-165">**Submitted by**</span></span>
- <span data-ttu-id="d5b2a-166">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-166">**Submission type**</span></span>
- <span data-ttu-id="d5b2a-167">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-167">**Status**</span></span>

![Параметры фильтрации отправок администраторами](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="d5b2a-169">Чтобы экспортировать результаты, нажмите **кнопку Экспорт** в верхней части страницы и выберите **"Данные диаграммы"** или **"Таблица".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d5b2a-170">Сохраните CSV-файл в появившемся диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="d5b2a-171">Под графиком доступны три **вкладки:** "Электронная почта" (по умолчанию), **URL-адрес**и **вложение.**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="d5b2a-172">Просмотр отправок электронной почты администратора</span><span class="sxs-lookup"><span data-stu-id="d5b2a-172">View admin email submissions</span></span>

<span data-ttu-id="d5b2a-173">Перейдите на **вкладку "Электронная** почта".</span><span class="sxs-lookup"><span data-stu-id="d5b2a-173">Click the **Email** tab.</span></span>

<span data-ttu-id="d5b2a-174">Чтобы добавить столбцы **в представление или удалить** их из него, нажмите кнопку параметров столбца в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d5b2a-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-175">**Date**</span></span>
- <span data-ttu-id="d5b2a-176">**Идентификатор отправки**— значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="d5b2a-177">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-178">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-179">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-179">**Sender**</span></span>
- <span data-ttu-id="d5b2a-180">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-181">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-181">**Submission type**</span></span>
- <span data-ttu-id="d5b2a-182">**Причина доставки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-182">**Delivery reason**</span></span>
- <span data-ttu-id="d5b2a-183">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-184">**Тип элемента управления**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-184">**Control type**</span></span>
- <span data-ttu-id="d5b2a-185">**Источник элементов управления**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-185">**Control source**</span></span>

  <span data-ttu-id="d5b2a-186"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="d5b2a-187">Просмотр отправок URL-адресов администратора</span><span class="sxs-lookup"><span data-stu-id="d5b2a-187">View admin URL submissions</span></span>

<span data-ttu-id="d5b2a-188">Перейдите на **вкладку** URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-188">Click the **URL** tab.</span></span>

<span data-ttu-id="d5b2a-189">Чтобы добавить столбцы **в представление или удалить** их из него, нажмите кнопку параметров столбца в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d5b2a-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-190">**Date**</span></span>
- <span data-ttu-id="d5b2a-191">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-191">**Submission ID**</span></span>
- <span data-ttu-id="d5b2a-192">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-194">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-194">**Submission type**</span></span>
- <span data-ttu-id="d5b2a-195">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d5b2a-196"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="d5b2a-197">Просмотр отправок администратора</span><span class="sxs-lookup"><span data-stu-id="d5b2a-197">View admin attachment submissions</span></span>

<span data-ttu-id="d5b2a-198">Перейдите на **вкладку "Вложения".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="d5b2a-199">Чтобы добавить столбцы **в представление или удалить** их из него, нажмите кнопку параметров столбца в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d5b2a-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-200">**Date**</span></span>
- <span data-ttu-id="d5b2a-201">**Идентификатор отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-201">**Submission ID**</span></span>
- <span data-ttu-id="d5b2a-202">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-203">**Имя файла**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-204">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-204">**Submission type**</span></span>
- <span data-ttu-id="d5b2a-205">**Состояние**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d5b2a-206"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="d5b2a-207">Просмотр пользовательских отправок в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d5b2a-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="d5b2a-208">Если вы развернули надстройку [Report Message](enable-the-report-message-add-in.md)или пользователи используют встроенную отчетность в Outlook [в Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие пользователи отчеты делятся на **вкладке "Отправки пользователем".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="d5b2a-209">В Центре безопасности & требованиям перейдите в раздел **Отправки в** \> **управлении угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="d5b2a-210">Выберите **вкладку "Отправленные пользователи"** и щелкните **"Создать отправку".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="d5b2a-211">Чтобы добавить столбцы **в представление или удалить** их из него, нажмите кнопку параметров столбца в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d5b2a-212">**Submitted on**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-212">**Submitted on**</span></span>
- <span data-ttu-id="d5b2a-213">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-214">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-215">**Sender**</span></span>
- <span data-ttu-id="d5b2a-216">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-217">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-217">**Submission type**</span></span>

<span data-ttu-id="d5b2a-218"><sup>\*</sup> При нажатии этого значения подробные сведения отображаются во всплывающем элементе.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="d5b2a-219">В верхней части страницы можно ввести начальную и конечный дату и (по умолчанию) отфильтровать **элементы по отправителю,** введя значение в поле и нажимая ![ кнопку "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="d5b2a-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d5b2a-220">Update</span><span class="sxs-lookup"><span data-stu-id="d5b2a-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d5b2a-221">Чтобы изменить условия фильтра, нажмите **кнопку «Отправитель»** и выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d5b2a-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="d5b2a-222">**Домен отправителя**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-222">**Sender domain**</span></span>
- <span data-ttu-id="d5b2a-223">**Тема**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-223">**Subject**</span></span>
- <span data-ttu-id="d5b2a-224">**Кем отправлено**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-224">**Submitted by**</span></span>
- <span data-ttu-id="d5b2a-225">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-225">**Submission type**</span></span>
- <span data-ttu-id="d5b2a-226">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-226">**Sender IP**</span></span>

![Параметры фильтра для отправок пользователем](../../media/user-submissions-filter-options.png)

<span data-ttu-id="d5b2a-228">Чтобы экспортировать результаты, нажмите **кнопку Экспорт** в верхней части страницы и выберите **"Данные диаграммы"** или **"Таблица".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d5b2a-229">Сохраните CSV-файл в появившемся диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="d5b2a-230">Просмотр пользовательских отправок в настраиваемый почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="d5b2a-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="d5b2a-231">Если настраиваемый [почтовый ящик настроен на получение сообщений](user-submission.md) из которых были включены, вы можете просматривать и отправлять сообщения, доставленные в почтовый ящик отчетов.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="d5b2a-232">В Центре безопасности & требованиям перейдите в раздел **Отправки в** \> **управлении угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="d5b2a-233">Перейдите на **вкладку "Настраиваемый почтовый** ящик".</span><span class="sxs-lookup"><span data-stu-id="d5b2a-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="d5b2a-234">Чтобы добавить столбцы **в представление или удалить** их из него, нажмите кнопку параметров столбца в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d5b2a-235">**Submitted on**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-235">**Submitted on**</span></span>
- <span data-ttu-id="d5b2a-236">**Кем отправлено**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-237">**Тема**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-238">**Sender**</span></span>
- <span data-ttu-id="d5b2a-239">**IP-адрес отправителя**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d5b2a-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d5b2a-240">**Тип отправки**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-240">**Submission type**</span></span>

<span data-ttu-id="d5b2a-241">В верхней части страницы можно ввести начальную и дату окончания; отфильтровать данные по **дате "Отправить"** введите значение в поле и нажмите ![ кнопку "Обновить". ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="d5b2a-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d5b2a-242">Update</span><span class="sxs-lookup"><span data-stu-id="d5b2a-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d5b2a-243">Чтобы экспортировать результаты, нажмите **кнопку Экспорт** в верхней части страницы и выберите **"Данные диаграммы"** или **"Таблица".**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d5b2a-244">Сохраните CSV-файл в появившемся диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="d5b2a-245">Отправка сообщений в Майкрософт из настраиваемого почтового ящика</span><span class="sxs-lookup"><span data-stu-id="d5b2a-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="d5b2a-246">Если вы настроили пользовательский почтовый ящик для перехвата пользовательских сообщений без отправки сообщений в корпорацию Майкрософт, то вы можете найти и отправить определенные сообщения корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="d5b2a-247">Это эффективно перемещает отправку пользователя в отправку с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="d5b2a-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="d5b2a-248">На **вкладке "Настраиваемый** почтовый ящик" выберите сообщение в списке, нажмите **кнопку «Действие»** и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d5b2a-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="d5b2a-249">**Очистка отчетов**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-249">**Report clean**</span></span>
- <span data-ttu-id="d5b2a-250">**Фишинг отчетов**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-250">**Report phishing**</span></span>
- <span data-ttu-id="d5b2a-251">**Сообщение о вредоносной**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-251">**Report malware**</span></span>
- <span data-ttu-id="d5b2a-252">**Сообщать о нежелательной почт**</span><span class="sxs-lookup"><span data-stu-id="d5b2a-252">**Report spam**</span></span>

![Параметры кнопки действия](../../media/user-submission-custom-mailbox-action-button.png)
