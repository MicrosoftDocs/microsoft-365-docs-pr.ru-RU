---
title: Отправка сообщений вручную в корпорацию Майкрософт для анализа
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: Администраторы и конечные пользователи могут узнать, как отправлять сообщения электронной почты (хорошая почта помечена как "пустая" или "не пустая") корпорации Майкрософт для анализа.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94747b1d0a1aef746a63abada977aa47270ae4e2
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865084"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="ab901-103">Отправка сообщений вручную в корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="ab901-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ab901-104">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab901-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ab901-105">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ab901-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="ab901-106">Это может быть очень сложно, если пользователи в вашей организации получают нежелательные сообщения (спам) или фишинговые сообщения в папке "Входящие" или не получают подлинных сообщений электронной почты, так как они помечены как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="ab901-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="ab901-107">Мы постоянно настраиваем фильтры нежелательной почты, чтобы они были более точными.</span><span class="sxs-lookup"><span data-stu-id="ab901-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="ab901-108">Вы и ваши пользователи можете помочь в этом, поверив ложные срабатывания (хорошая электронная почта помечена как пустая), ложные отрицательные результаты (разрешена неверная почта) и фишинговые сообщения корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="ab901-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="ab901-109">Из-за большого объема получаемой отправки мы можем не отвечать на все запросы на анализ.</span><span class="sxs-lookup"><span data-stu-id="ab901-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="ab901-110">Отправка ложных отрицательных результатов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ab901-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="ab901-111">Вместо использования следующих процедур для сообщения о ложных отрицательных результатов пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="ab901-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="ab901-112">Сведения об установке и использовании этих средств см. в подстройках ["Включить](enable-the-report-message-add-in.md) сообщение отчета" и "Включить надстройку report [Phishing".](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="ab901-112">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="ab901-113">Если вы получили сообщение, которое прошло фильтрацию нежелательной почты, которое должно было быть определено как спам или фишинг, вы можете отправить его в группы анализа нежелательной почты Майкрософт и Анализа фишинга Майкрософт соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="ab901-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="ab901-114">Аналитики проверяют сообщение и добавляют его в фильтры для всей службы, если оно соответствует критериям классификации.</span><span class="sxs-lookup"><span data-stu-id="ab901-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="ab901-115">Создайте пустое сообщение электронной почты с одним из следующих получателей:</span><span class="sxs-lookup"><span data-stu-id="ab901-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="ab901-116">**Нежелаемая почта:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ab901-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="ab901-117">**Фишинг :**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ab901-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="ab901-118">Перетащите нежелательное или фишинговое сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="ab901-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="ab901-119">Это позволит сохранить нежелательное или фишинговое сообщение в виде вложения в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="ab901-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="ab901-120">Не копируйте и не вдавлийте содержимое сообщения или переназначайте его (нам нужно исходное сообщение, чтобы мы могли проверить его заглавные тексты).</span><span class="sxs-lookup"><span data-stu-id="ab901-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="ab901-121">В новое сообщение можно вкрепить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab901-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="ab901-122">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные.</span><span class="sxs-lookup"><span data-stu-id="ab901-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="ab901-123">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="ab901-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="ab901-124">Используйте формат MSG (формат Outlook по умолчанию) или EML (формат Outlook в Интернете по умолчанию) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab901-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="ab901-125">По завершению нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="ab901-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="ab901-126">У администраторов есть несколько различных способов блокировки определенных сообщений, ошибочно определенных как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="ab901-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="ab901-127">Дополнительные сведения см. в сведениях о создании [списков заблокированных отправитель в EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ab901-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="ab901-128">Отправка ложных срабатывавай в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ab901-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="ab901-129">Вместо использования следующих процедур для сообщения о ложных срабатываниях пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="ab901-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="ab901-130">Сведения об установке и использовании этих средств см. в подстройках ["Включить](enable-the-report-message-add-in.md) сообщение отчета" и "Включить надстройку report [Phishing".](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="ab901-130">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="ab901-131">Если сообщение было неправильно определено как нежелательное, его можно отправить группе анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ab901-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="ab901-132">Аналитики проанализируют сообщение и (в зависимости от результатов анализа) можно скорректировать фильтры для всей службы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="ab901-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="ab901-133">Создайте пустое сообщение электронной почты с `not_junk@office365.microsoft.com` получателем:</span><span class="sxs-lookup"><span data-stu-id="ab901-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="ab901-134">Перетащите неправильное сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="ab901-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="ab901-135">Это позволит сохранить неправильное сообщение в качестве вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="ab901-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="ab901-136">Не копируйте и не вдайте содержимое сообщения или переададантируйте его (нам нужно исходное сообщение, чтобы мы могли проверить его заглавные тексты).</span><span class="sxs-lookup"><span data-stu-id="ab901-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="ab901-137">В новое сообщение можно вкрепить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab901-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="ab901-138">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные.</span><span class="sxs-lookup"><span data-stu-id="ab901-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="ab901-139">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="ab901-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="ab901-140">Используйте формат MSG (формат Outlook по умолчанию) или EML (формат Outlook в Интернете по умолчанию) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab901-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="ab901-141">По завершению нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="ab901-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="ab901-142">Администраторы могут использовать несколько различных способов пропуска фильтрации нежелательной почты для определенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab901-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="ab901-143">Дополнительные сведения см. в сведениях [о создании списков надежных отправников в EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ab901-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="ab901-144">Где хранятся данные от отправленных в Корпорацию Майкрософт данных?</span><span class="sxs-lookup"><span data-stu-id="ab901-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="ab901-145">Данные находятся на границе соответствия требованиям Office 365 в центрах обработки данных в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="ab901-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="ab901-146">Данные проверяются аналитиками из группы разработки для повышения эффективности фильтров.</span><span class="sxs-lookup"><span data-stu-id="ab901-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="ab901-147">Создание правила потока почты для получения копий сообщений, отправленных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ab901-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="ab901-148">Инструкции см. в инструкциях по использованию правил потока почты, чтобы узнать, что ваши [пользователи сообщают корпорации Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ab901-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
