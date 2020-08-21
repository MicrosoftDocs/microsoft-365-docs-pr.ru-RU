---
title: Отправка сообщений корпорации Майкрософт для анализа вручную
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
description: Администраторы и конечные пользователи могут узнать, как сообщения электронной почты (помеченные как недопустимые или неправильные письма) в корпорацию Майкрософт для анализа.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f00f8399164a84d2cb9dae0c4c416b73dfb0dc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827813"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="dc21a-103">Отправка сообщений корпорации Майкрософт для анализа вручную</span><span class="sxs-lookup"><span data-stu-id="dc21a-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="dc21a-104">Если вы являетесь администратором организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dc21a-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="dc21a-105">Дополнительные сведения см. в статье ["Использование функции отправки администратора" для отправки подозрительного спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="dc21a-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="dc21a-106">Это может создавать раздражение, если пользователи в организации получают нежелательные сообщения или фишинговые сообщения в папке "Входящие" или не получает допустимые сообщения, так как они помечаются как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="dc21a-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="dc21a-107">Мы постоянно точно подстраиваем фильтры нежелательной почты для более точной настройки.</span><span class="sxs-lookup"><span data-stu-id="dc21a-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="dc21a-108">Вы и ваши пользователи могут помочь сделать этот процесс, отправляя ложные срабатывания (если в качестве плохого сообщения электронной почты указаны недопустимые), ложные отрицательные отрицательные (разрешены неправильные письма) и фишинговые сообщения в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="dc21a-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="dc21a-109">Из-за большого объема получаемых отправленных отправок нам удалось отвечать на все запросы для анализа.</span><span class="sxs-lookup"><span data-stu-id="dc21a-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="dc21a-110">Отправка ложных отрицательных возможностей в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dc21a-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="dc21a-111">Вместо использования следующих процедур для сообщения о ложных отрицательных результатах пользователи в Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку Report Message для Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="dc21a-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="dc21a-112">Сведения об установке и использовании этого средства см. в разделе ["Включение надстройки Report Message".](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="dc21a-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="dc21a-113">Если вы получаете сообщение, прошедшее через фильтрацию нежелательной почты, которая должна быть определенным как спам или фишинг, при необходимости его можно отправить в группы анализа нежелательной почты и Microsoft Phishing.</span><span class="sxs-lookup"><span data-stu-id="dc21a-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="dc21a-114">Эти результаты проверяют сообщение и добавят его в фильтры на уровне службы, если оно соответствует условиям классификации.</span><span class="sxs-lookup"><span data-stu-id="dc21a-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="dc21a-115">Создайте пустое сообщение электронной почты одним из следующих получателей:</span><span class="sxs-lookup"><span data-stu-id="dc21a-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="dc21a-116">**Junk**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="dc21a-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="dc21a-117">**Фишинг:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="dc21a-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="dc21a-118">Перетащите нежелательное или фишинговое сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="dc21a-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="dc21a-119">Таким образом нежелательное или фишинговое сообщение будет сохранено в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="dc21a-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="dc21a-120">Не копируйте и не вставляйте содержимое сообщения или переслайте его (нам необходимо исходное сообщение для проверки заголовков сообщения).</span><span class="sxs-lookup"><span data-stu-id="dc21a-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="dc21a-121">В новое сообщение можно вложить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc21a-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="dc21a-122">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные.</span><span class="sxs-lookup"><span data-stu-id="dc21a-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="dc21a-123">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="dc21a-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="dc21a-124">Используйте формат MSG (стандартный формат Outlook) или EML (формат Outlook в Интернете по умолчанию) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc21a-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="dc21a-125">По завершении нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="dc21a-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="dc21a-126">У администраторов есть несколько различных способов блокировки определенных сообщений, которые не выявлены как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="dc21a-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="dc21a-127">Дополнительные сведения см. в статье ["Создание списков заблокированных отправителей в EOP".](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="dc21a-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="dc21a-128">Отправка сообщений о ложных срабатываниях в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dc21a-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="dc21a-129">Вместо использования следующих процедур для сообщения о ложных срабатываниях пользователи в Outlook и Outlook в Интернете могут использовать надстройку Report Message для Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="dc21a-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="dc21a-130">Сведения об установке и использовании этого средства см. в разделе ["Включение надстройки Report Message".](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="dc21a-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="dc21a-131">Если сообщение было неправильно указано как спам, вы можете отправить его в группу анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dc21a-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="dc21a-132">Аналитики оценивают сообщение и (в зависимости от результатов анализа) можно настроить фильтры для всей службы, чтобы разрешить доставку сообщения.</span><span class="sxs-lookup"><span data-stu-id="dc21a-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="dc21a-133">Создайте пустое сообщение с `not_junk@office365.microsoft.com` адресом:</span><span class="sxs-lookup"><span data-stu-id="dc21a-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="dc21a-134">Перетащите неопределенное сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="dc21a-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="dc21a-135">При этом пропущенное сообщение будет сохранено в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="dc21a-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="dc21a-136">Не копируйте и не вставляйте содержимое сообщения или переслайте его (нам необходимо исходное сообщение для проверки заголовков сообщения).</span><span class="sxs-lookup"><span data-stu-id="dc21a-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="dc21a-137">В новое сообщение можно вложить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc21a-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="dc21a-138">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные.</span><span class="sxs-lookup"><span data-stu-id="dc21a-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="dc21a-139">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="dc21a-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="dc21a-140">Используйте формат MSG (стандартный формат Outlook) или EML (формат Outlook в Интернете по умолчанию) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc21a-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="dc21a-141">По завершении нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="dc21a-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="dc21a-142">Администраторам доступно несколько различных способов разрешить определенным сообщениям пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="dc21a-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="dc21a-143">Дополнительные сведения см. в статье ["Создание списков надежных отправителей в EOP".](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="dc21a-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="dc21a-144">Создание правила потока обработки почты для получения копий сообщений, о которых будут отправлены в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dc21a-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="dc21a-145">Инструкции см. в статье ["Использование правил для потока обработки почты", чтобы узнать, что пользователи подчиникают в Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="dc21a-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
