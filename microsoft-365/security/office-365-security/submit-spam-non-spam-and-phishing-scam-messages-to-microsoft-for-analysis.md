---
title: Отправка сообщений в корпорацию Майкрософт для анализа вручную
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Вы и ваши пользователи могут отправлять ложные сообщения о нежелательной почте в корпорацию Майкрософт для анализа. '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032808"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="a3010-103">Отправка сообщений в корпорацию Майкрософт для анализа вручную</span><span class="sxs-lookup"><span data-stu-id="a3010-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="a3010-104">Если вы являетесь администратором в организации Office 365 с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3010-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="a3010-105">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a3010-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a3010-106">Может быть непонятно, когда пользователи в вашей организации получают нежелательные сообщения или фишинговые сообщения в их папке "Входящие" или если они не получили легальное сообщение электронной почты, так как отмечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="a3010-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="a3010-107">Мы постоянно намерены настраивать фильтры нежелательной почты, чтобы они были более точными.</span><span class="sxs-lookup"><span data-stu-id="a3010-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="a3010-108">Вы и ваши пользователи могут помочь этому процессу, отправив ложные срабатывания (хорошее сообщение отмечено как плохое), ложные отрицательные отрицательные (недопустимые почты) и фишинговые сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="a3010-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="a3010-109">Из-за большого объема получаемых данных мы не можем ответить на все запросы на анализ.</span><span class="sxs-lookup"><span data-stu-id="a3010-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="a3010-110">Передача ложных негативных результатов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3010-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a3010-111">Вместо того чтобы сообщать о ложных отрицательных значениях, пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку сообщения отчета для Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="a3010-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="a3010-112">Сведения об установке и использовании этого средства приведены [в разделе Включение надстройки Report Message](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a3010-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="a3010-113">Если вы получаете сообщение, прошедшее с помощью фильтрации нежелательной почты, которое должно быть определено как нежелательная почта или фишинг, вы можете отправить сообщение в Microsoft спама и Microsoft фишинга, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="a3010-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="a3010-114">Аналитики просматривают сообщение и добавляют его к фильтрам на уровне службы, если он соответствует критериям классификации.</span><span class="sxs-lookup"><span data-stu-id="a3010-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="a3010-115">Создайте новое пустое сообщение электронной почты с одним из следующих получателей:</span><span class="sxs-lookup"><span data-stu-id="a3010-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="a3010-116">**Нежелательная почта**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a3010-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="a3010-117">**Фишинг**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a3010-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="a3010-118">Перетащите нежелательное или мошенническое сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="a3010-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="a3010-119">Это приведет к сохранению нежелательного или фишингового сообщения в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="a3010-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="a3010-120">Не копируйте и не вставляйте содержимое сообщения или пересылаете сообщение (вам нужно исходное сообщение, чтобы мы могли проверить заголовки сообщений).</span><span class="sxs-lookup"><span data-stu-id="a3010-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="a3010-121">В новое сообщение можно вложить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="a3010-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a3010-122">Убедитесь, что все сообщения имеют один и тот же тип: фишинговые или нежелательные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a3010-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="a3010-123">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="a3010-123">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="a3010-124">Используйте формат MSG (формат Outlook) или EML (по умолчанию Outlook в Интернете) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a3010-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="a3010-125">Когда все будет готово, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a3010-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a3010-126">Администраторы имеют несколько различных способов блокирования определенных сообщений, которые неопознаны как спам.</span><span class="sxs-lookup"><span data-stu-id="a3010-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="a3010-127">Дополнительные сведения см. [в статье Создание заблокированных списков отправителей в Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a3010-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="a3010-128">Передача ложных срабатываний в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3010-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a3010-129">Вместо использования следующих процедур для создания отчетов о ложных срабатываниях, пользователи в Outlook и Outlook в Интернете могут использовать надстройку сообщения отчета для Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="a3010-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="a3010-130">Сведения об установке и использовании этого средства приведены [в разделе Включение надстройки Report Message](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a3010-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="a3010-131">Если сообщение было ошибочно определено как спам, вы можете отправлять сообщение в группу анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3010-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a3010-132">Аналитики оценивают сообщение и (в зависимости от результатов анализа) фильтры, которые могут быть настроены на уровне службы, чтобы разрешить сообщения.</span><span class="sxs-lookup"><span data-stu-id="a3010-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="a3010-133">Создание нового пустого сообщения электронной почты с `not_junk@office365.microsoft.com` получателем:</span><span class="sxs-lookup"><span data-stu-id="a3010-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="a3010-134">Перетащите неопознанное сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="a3010-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="a3010-135">Это приведет к сохранению неопознанного сообщения в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="a3010-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="a3010-136">Не копируйте и не вставляйте содержимое сообщения или пересылаете сообщение (вам нужно исходное сообщение, чтобы мы могли проверить заголовки сообщений).</span><span class="sxs-lookup"><span data-stu-id="a3010-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="a3010-137">В новое сообщение можно вложить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="a3010-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a3010-138">Убедитесь, что все сообщения имеют один и тот же тип: фишинговые или нежелательные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a3010-138">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="a3010-139">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="a3010-139">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="a3010-140">Используйте формат MSG (формат Outlook) или EML (по умолчанию Outlook в Интернете) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a3010-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="a3010-141">Когда все будет готово, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="a3010-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a3010-142">Администраторы имеют несколько различных способов, позволяющих определенным сообщениям пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a3010-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="a3010-143">Дополнительные сведения см. [в статье Создание списков надежных отправителей в Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a3010-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="a3010-144">Создание правила обработки почтового ящика для получения копий сообщений, отправленных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3010-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="a3010-145">Вы можете создать правило для обработки почтового ящика (также называемое правилом транспорта), которое ищет сообщения электронной почты, отправленные в корпорацию Майкрософт, с помощью методов, описанных в этой статье, и вы можете настроить получателей скрытой копии для получения копий этих сообщений, о которых получено сообщение.</span><span class="sxs-lookup"><span data-stu-id="a3010-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="a3010-146">Вы можете создать правило для почтового процесса в центре администрирования Exchange и PowerShell (Exchange Online PowerShell для Office 365). Exchange Online Protection PowerShell для автономных клиентов EOP).</span><span class="sxs-lookup"><span data-stu-id="a3010-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3010-147">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a3010-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3010-148">Прежде чем выполнять эти процедуры, вам необходимо назначить разрешения в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3010-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="a3010-149">В частности, необходимо назначить роль " **правила транспорта** ", которая назначается для ролей управления **организацией**, **управления соответствием требованиям**и управления **записями** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a3010-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="a3010-150">Дополнительные сведения см. в статье [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="a3010-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="a3010-151">Чтобы открыть центр администрирования Exchange в Exchange Online, обратитесь к [центру администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a3010-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="a3010-152">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a3010-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a3010-153">Сведения о подключении к автономной службе Exchange Online Protection PowerShell см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a3010-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a3010-154">Дополнительные сведения о правилах обработки почтового ящика в Exchange Online и отдельном EOP содержатся в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a3010-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="a3010-155">Правила потока обработки почты (правила транспорта) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3010-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="a3010-156">Условия и исключения правила для обработки почтового процесса (предикаты) в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3010-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="a3010-157">Действия правил обработки почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3010-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="a3010-158">Использование центра администрирования Exchange для создания правила обработки почтового ящика для получения копий отчетных сообщений</span><span class="sxs-lookup"><span data-stu-id="a3010-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="a3010-159">В Центре администрирования Exchange перейдите в раздел **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="a3010-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="a3010-160">Щелкните **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png) добавить, а затем выберите **создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="a3010-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="a3010-161">На открывшейся странице **Новое правило** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a3010-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a3010-162">**Name**: введите уникальное описательное имя правила.</span><span class="sxs-lookup"><span data-stu-id="a3010-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="a3010-163">Например, сообщения скрытой копии в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3010-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="a3010-164">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="a3010-164">Click **More Options**.</span></span>

   - <span data-ttu-id="a3010-165">**Применять это правило, если**: выберите адрес **получателя** \> **содержит любое из этих слов**: в появившемся диалоговом окне **Укажите слова или фразы** введите одно из следующих значений, нажмите **Добавить** ![значок](../../media/ITPro-EAC-AddIcon.png)"Добавить" и повторяйте до тех пор, пока не ввели все значения.</span><span class="sxs-lookup"><span data-stu-id="a3010-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="a3010-166">Чтобы изменить запись, выберите ее и нажмите кнопку **изменить** ![значок](../../media/ITPro-EAC-EditIcon.png)редактирования.</span><span class="sxs-lookup"><span data-stu-id="a3010-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="a3010-167">Чтобы удалить запись, выберите ее и нажмите кнопку **Удалить** ![значок](../../media/ITPro-EAC-DeleteIcon.png)"Удалить".</span><span class="sxs-lookup"><span data-stu-id="a3010-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="a3010-168">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a3010-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="a3010-169">**Выполните следующие**действия: выберите **добавить получателей** \> **в поле "СК**".</span><span class="sxs-lookup"><span data-stu-id="a3010-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="a3010-170">В появившемся диалоговом окне найдите и выберите получателей, которых вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="a3010-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="a3010-171">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a3010-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="a3010-172">Вы можете выбрать дополнительные параметры для аудита правила, проверки правила, активации правила в течение определенного периода времени и других параметров.</span><span class="sxs-lookup"><span data-stu-id="a3010-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="a3010-173">Рекомендуем проверить правило перед его применением.</span><span class="sxs-lookup"><span data-stu-id="a3010-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="a3010-174">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3010-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="a3010-175">Создание правила для обработки почтового сообщения для получения копий отчетов с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3010-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="a3010-176">В этом примере создается правило для почтового процесса с именем BCC messages, отправленное в корпорацию Майкрософт, которое ищет сообщения электронной почты, сообщаемые в корпорацию Майкрософт, с помощью методов, описанных в этом разделе, и добавляет пользователей laura@contoso.com и julia@contoso.com как получателей скрытой копии.</span><span class="sxs-lookup"><span data-stu-id="a3010-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="a3010-177">Дополнительные сведения о синтаксисе и параметрах см. в статье [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="a3010-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a3010-178">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="a3010-178">How do you know this worked?</span></span>

<span data-ttu-id="a3010-179">Чтобы убедиться, что вы настроили правила обработки почты для получения копий сообщений, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a3010-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="a3010-180">В центре администрирования Exchange перейдите к разделу **правила** \> для обработки **почтового ящика** \> ,](../../media/ITPro-EAC-EditIcon.png)выберите правило \> щелкните **изменить** ![значок редактирования и проверьте параметры.</span><span class="sxs-lookup"><span data-stu-id="a3010-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="a3010-181">В PowerShell выполните следующую команду, чтобы проверить параметры:</span><span class="sxs-lookup"><span data-stu-id="a3010-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="a3010-182">Отправьте тестовые сообщения на один из электронных адресов отчетов и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="a3010-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
