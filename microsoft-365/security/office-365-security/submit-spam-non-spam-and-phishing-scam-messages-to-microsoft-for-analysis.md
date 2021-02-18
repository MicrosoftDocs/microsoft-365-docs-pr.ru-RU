---
title: Отправка сообщений вручную в корпорацию Майкрософт для анализа
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Администраторы и конечные пользователи могут узнать, как отправлять сообщения электронной почты (хорошая почта помечена как "пустая" или "не пустая") корпорации Майкрософт для анализа.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290373"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="75d96-103">Отправка сообщений вручную в корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="75d96-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="75d96-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="75d96-104">**Applies to**</span></span>
- [<span data-ttu-id="75d96-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="75d96-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="75d96-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="75d96-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="75d96-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75d96-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="75d96-108">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="75d96-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="75d96-109">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="75d96-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="75d96-110">Это может быть очень сложно, если пользователи в вашей организации получают нежелательные сообщения (спам) или фишинговые сообщения в папке "Входящие" или не получают подлинных сообщений электронной почты, так как они помечены как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="75d96-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="75d96-111">Мы постоянно настраиваем фильтры нежелательной почты для более точной настройки.</span><span class="sxs-lookup"><span data-stu-id="75d96-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="75d96-112">Вы и ваши пользователи можете помочь в этом, поверив ложные срабатывания (хорошая электронная почта помечена как пустая), ложные отрицательные результаты (разрешена неверная почта) и фишинговые сообщения корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="75d96-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="75d96-113">Из-за большого объема получаемой отправки мы можем не отвечать на все запросы на анализ.</span><span class="sxs-lookup"><span data-stu-id="75d96-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="75d96-114">Отправка ложных отрицательных результатов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="75d96-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="75d96-115">Вместо использования следующих процедур для сообщения о ложных отрицательных результатов пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="75d96-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="75d96-116">Сведения об установке и использовании этих средств см. в подстройках ["Включить](enable-the-report-message-add-in.md) сообщение отчета" и "Включить надстройку report [Phishing".](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="75d96-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="75d96-117">Если вы получили сообщение, которое прошло фильтрацию нежелательной почты, которое должно было быть определено как спам или фишинг, вы можете отправить его в группы анализа нежелательной почты Майкрософт и Анализа фишинга Майкрософт соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="75d96-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="75d96-118">Аналитики проверяют сообщение и добавляют его в фильтры для всей службы, если оно соответствует критериям классификации.</span><span class="sxs-lookup"><span data-stu-id="75d96-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="75d96-119">Создайте пустое сообщение электронной почты с одним из следующих получателей:</span><span class="sxs-lookup"><span data-stu-id="75d96-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="75d96-120">**Нежелаемая почта:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="75d96-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="75d96-121">**Фишинг :**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="75d96-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="75d96-122">Перетащите нежелательное или фишинговое сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="75d96-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="75d96-123">Это позволит сохранить нежелательное или фишинговое сообщение в виде вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="75d96-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="75d96-124">Не копируйте и не вдавлийте содержимое сообщения или переназначайте его (нам нужно исходное сообщение, чтобы мы могли проверить его заглавные тексты).</span><span class="sxs-lookup"><span data-stu-id="75d96-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="75d96-125">В новое сообщение можно вкрепить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="75d96-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="75d96-126">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные.</span><span class="sxs-lookup"><span data-stu-id="75d96-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="75d96-127">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="75d96-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="75d96-128">Используйте формат MSG (формат Outlook по умолчанию) или EML (формат Outlook в Интернете по умолчанию) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="75d96-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="75d96-129">По завершению нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="75d96-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="75d96-130">У администраторов есть несколько различных способов блокировки определенных сообщений, ошибочно определенных как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="75d96-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="75d96-131">Дополнительные сведения см. в сведениях о создании [списков заблокированных отправитель в EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="75d96-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="75d96-132">Отправка ложных срабатывавай в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="75d96-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="75d96-133">Вместо использования следующих процедур для сообщения о ложных срабатываниях пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="75d96-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="75d96-134">Сведения об установке и использовании этих средств см. в подстройках ["Включить](enable-the-report-message-add-in.md) сообщение отчета" и "Включить надстройку report [Phishing".](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="75d96-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="75d96-135">Если сообщение было неправильно определено как нежелательное, его можно отправить группе анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="75d96-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="75d96-136">Аналитики проанализируют сообщение и (в зависимости от результатов анализа) можно скорректировать фильтры для всей службы, чтобы разрешить его.</span><span class="sxs-lookup"><span data-stu-id="75d96-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="75d96-137">Создайте пустое сообщение электронной почты с `not_junk@office365.microsoft.com` получателем:</span><span class="sxs-lookup"><span data-stu-id="75d96-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="75d96-138">Перетащите неправильное сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="75d96-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="75d96-139">Это позволит сохранить неправильное сообщение в качестве вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="75d96-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="75d96-140">Не копируйте и не вдавлийте содержимое сообщения или переназначайте его (нам нужно исходное сообщение, чтобы мы могли проверить его заглавные тексты).</span><span class="sxs-lookup"><span data-stu-id="75d96-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="75d96-141">В новое сообщение можно вкрепить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="75d96-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="75d96-142">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные.</span><span class="sxs-lookup"><span data-stu-id="75d96-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="75d96-143">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="75d96-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="75d96-144">Используйте формат MSG (формат Outlook по умолчанию) или EML (формат Outlook в Интернете по умолчанию) для вложенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="75d96-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="75d96-145">По завершению нажмите кнопку **"Отправить".**</span><span class="sxs-lookup"><span data-stu-id="75d96-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="75d96-146">Администраторы могут использовать несколько различных способов пропуска фильтрации нежелательной почты для определенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="75d96-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="75d96-147">Дополнительные сведения см. в сведениях [о создании списков надежных отправников в EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="75d96-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="75d96-148">Где хранятся данные от отправленных в Корпорацию Майкрософт данных?</span><span class="sxs-lookup"><span data-stu-id="75d96-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="75d96-149">Данные находятся на границе соответствия требованиям Office 365 в центрах обработки данных в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="75d96-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="75d96-150">Данные проверяются аналитиками из группы разработки для повышения эффективности фильтров.</span><span class="sxs-lookup"><span data-stu-id="75d96-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="75d96-151">Создание правила потока почты для получения копий сообщений, отправленных в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="75d96-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="75d96-152">Инструкции см. в инструкциях по использованию правил потока почты, чтобы узнать, что ваши [пользователи сообщают корпорации Майкрософт.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="75d96-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
