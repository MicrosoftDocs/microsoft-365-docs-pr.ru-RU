---
title: Отправка сообщений в корпорацию Майкрософт для анализа вручную
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Администраторы и конечные пользователи могут узнать, как почтовые сообщения (хорошая почта, помеченная как плохая или плохая почта) в корпорацию Майкрософт для анализа.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6673dc7e7ac263ea9f734c002d0ffac410fadc07
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202207"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="003a6-103">Отправка сообщений в корпорацию Майкрософт для анализа вручную</span><span class="sxs-lookup"><span data-stu-id="003a6-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="003a6-104">Если вы являетесь администратором в Организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="003a6-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="003a6-105">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="003a6-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="003a6-106">Может быть непонятно, когда пользователи в вашей организации получают нежелательные сообщения или фишинговые сообщения в их папке "Входящие" или если они не получили легальное сообщение электронной почты, так как отмечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="003a6-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="003a6-107">Мы постоянно намерены настраивать фильтры нежелательной почты, чтобы они были более точными.</span><span class="sxs-lookup"><span data-stu-id="003a6-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="003a6-108">Вы и ваши пользователи могут помочь этому процессу, отправив ложные срабатывания (хорошее сообщение отмечено как плохое), ложные отрицательные отрицательные (недопустимые почты) и фишинговые сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="003a6-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="003a6-109">Из-за большого объема получаемых данных мы не можем ответить на все запросы на анализ.</span><span class="sxs-lookup"><span data-stu-id="003a6-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="003a6-110">Передача ложных негативных результатов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="003a6-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="003a6-111">Вместо того чтобы сообщать о ложных отрицательных значениях, пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку сообщения отчета для Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="003a6-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="003a6-112">Сведения об установке и использовании этого средства приведены [в разделе Включение надстройки Report Message](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="003a6-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="003a6-113">Если вы получаете сообщение, прошедшее с помощью фильтрации нежелательной почты, которое должно быть определено как нежелательная почта или фишинг, вы можете отправить сообщение в Microsoft спама и Microsoft фишинга, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="003a6-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="003a6-114">Аналитики просматривают сообщение и добавляют его к фильтрам на уровне службы, если он соответствует критериям классификации.</span><span class="sxs-lookup"><span data-stu-id="003a6-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="003a6-115">Создайте новое пустое сообщение электронной почты с одним из следующих получателей:</span><span class="sxs-lookup"><span data-stu-id="003a6-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="003a6-116">**Нежелательная почта**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="003a6-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="003a6-117">**Фишинг**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="003a6-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="003a6-118">Перетащите нежелательное или мошенническое сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="003a6-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="003a6-119">Это приведет к сохранению нежелательного или фишингового сообщения в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="003a6-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="003a6-120">Не копируйте и не вставляйте содержимое сообщения или пересылаете сообщение (вам нужно исходное сообщение, чтобы мы могли проверить заголовки сообщений).</span><span class="sxs-lookup"><span data-stu-id="003a6-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="003a6-121">В новое сообщение можно вложить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="003a6-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="003a6-122">Убедитесь, что все сообщения имеют один и тот же тип: сообщения фишинга или нежелательные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="003a6-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="003a6-123">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="003a6-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="003a6-124">Используйте формат MSG (формат Outlook) или EML (по умолчанию Outlook в Интернете) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="003a6-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="003a6-125">Когда все будет готово, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="003a6-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="003a6-126">Администраторы имеют несколько различных способов блокирования определенных сообщений, которые неопознаны как спам.</span><span class="sxs-lookup"><span data-stu-id="003a6-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="003a6-127">Дополнительные сведения см. [в разделе Создание заблокированных списков отправителей в EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="003a6-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="003a6-128">Передача ложных срабатываний в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="003a6-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="003a6-129">Вместо использования следующих процедур для создания отчетов о ложных срабатываниях, пользователи в Outlook и Outlook в Интернете могут использовать надстройку сообщения отчета для Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="003a6-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="003a6-130">Сведения об установке и использовании этого средства приведены [в разделе Включение надстройки Report Message](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="003a6-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="003a6-131">Если сообщение было ошибочно определено как спам, вы можете отправлять сообщение в группу анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="003a6-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="003a6-132">Аналитики оценивают сообщение и (в зависимости от результатов анализа) фильтры, которые могут быть настроены на уровне службы, чтобы разрешить сообщения.</span><span class="sxs-lookup"><span data-stu-id="003a6-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="003a6-133">Создание нового пустого сообщения электронной почты с `not_junk@office365.microsoft.com` получателем:</span><span class="sxs-lookup"><span data-stu-id="003a6-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="003a6-134">Перетащите неопознанное сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="003a6-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="003a6-135">Это приведет к сохранению неопознанного сообщения в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="003a6-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="003a6-136">Не копируйте и не вставляйте содержимое сообщения или пересылаете сообщение (вам нужно исходное сообщение, чтобы мы могли проверить заголовки сообщений).</span><span class="sxs-lookup"><span data-stu-id="003a6-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="003a6-137">В новое сообщение можно вложить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="003a6-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="003a6-138">Убедитесь, что все сообщения имеют один и тот же тип: сообщения фишинга или нежелательные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="003a6-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="003a6-139">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="003a6-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="003a6-140">Используйте формат MSG (формат Outlook) или EML (по умолчанию Outlook в Интернете) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="003a6-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="003a6-141">Когда все будет готово, нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="003a6-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="003a6-142">Администраторы имеют несколько различных способов, позволяющих определенным сообщениям пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="003a6-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="003a6-143">Дополнительные сведения см. [в статье Создание списков надежных отправителей в EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="003a6-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="003a6-144">Создание правила обработки почтового ящика для получения копий сообщений, отправленных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="003a6-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="003a6-145">Инструкции можно найти в статье [Использование правил для обработки почтового ящика для просмотра отчетов о пользователях в Майкрософт](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="003a6-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
