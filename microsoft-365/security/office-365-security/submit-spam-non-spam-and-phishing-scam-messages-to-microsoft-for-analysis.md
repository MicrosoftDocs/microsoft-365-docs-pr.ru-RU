---
title: Вручную отправлять сообщения в Корпорацию Майкрософт для анализа
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
description: Администраторы и конечные пользователи могут узнать, как отправлять сообщения электронной почты (хорошая почта помечена как плохая или плохая почта разрешена) в Корпорацию Майкрософт для анализа.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0d48c3c6f6d082085390d6e246a088b6d3f6bf0
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105552"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="9fc86-103">Вручную отправлять сообщения в Корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="9fc86-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9fc86-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="9fc86-104">**Applies to**</span></span>
- [<span data-ttu-id="9fc86-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9fc86-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9fc86-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="9fc86-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9fc86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9fc86-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="9fc86-108">Если вы администратор в организации с Exchange Online почтовыми ящиками, рекомендуем использовать страницу **Отправки** на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="9fc86-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the **Submissions** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="9fc86-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="9fc86-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="9fc86-110">Это может расстраивать, когда пользователи в вашей организации получают нежелательные сообщения (спам) или фишинговые сообщения в папке "Входящие", или если они не получают законное сообщение электронной почты, так как оно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="9fc86-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="9fc86-111">Мы постоянно настраиваем фильтры нежелательной почты, чтобы быть более точными.</span><span class="sxs-lookup"><span data-stu-id="9fc86-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="9fc86-112">Вы и ваши пользователи можете помочь этому процессу путем отправки ложных срабатывающих сообщений (хорошая электронная почта помечена как плохая), ложных негативов (разрешена плохая почта) и фишинговых сообщений в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="9fc86-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="9fc86-113">Из-за большого объема получаемой информации мы можем не отвечать на все запросы на анализ.</span><span class="sxs-lookup"><span data-stu-id="9fc86-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="9fc86-114">Отправка ложных негативов в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9fc86-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="9fc86-115">Вместо использования следующих процедур для сообщения о ложных негативах пользователи в Outlook и Outlook в Интернете (ранее известные как Outlook Web App) могут использовать надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="9fc86-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="9fc86-116">Сведения об установке и использовании этих средств см. в добавлении [Enable the Report Message](enable-the-report-message-add-in.md) и Enable the Report [Phishing add-in.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9fc86-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="9fc86-117">Если вы получили сообщение, которое прошло через фильтрацию нежелательной почты, которое должно было быть идентифицировано как спам или фишинг, вы можете отправить сообщение в группы анализа нежелательной почты и Microsoft Phishing Analysis по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="9fc86-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="9fc86-118">Аналитики рассмотрят сообщение и добавят его в фильтры для всей службы, если оно соответствует критериям классификации.</span><span class="sxs-lookup"><span data-stu-id="9fc86-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="9fc86-119">Создайте новое пустое сообщение электронной почты с одним из следующих получателей:</span><span class="sxs-lookup"><span data-stu-id="9fc86-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="9fc86-120">**Нежелательной**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="9fc86-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="9fc86-121">**Фишинг:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="9fc86-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="9fc86-122">Перетащите и сбросите нежелательное или фишинговое сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="9fc86-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="9fc86-123">Это позволит сохранить нежелательное или фишинговое сообщение в качестве вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="9fc86-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="9fc86-124">Не копируйте и не вдергируйте содержимое сообщения или переад. (нам нужно исходное сообщение, чтобы мы могли проверить заглавные книги сообщений).</span><span class="sxs-lookup"><span data-stu-id="9fc86-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="9fc86-125">В новом сообщении можно прикрепить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="9fc86-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="9fc86-126">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9fc86-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="9fc86-127">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="9fc86-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="9fc86-128">Используйте форматы .msg (формат Outlook по умолчанию) или .eml (Outlook в веб-формате) для подключенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="9fc86-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="9fc86-129">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="9fc86-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="9fc86-130">Администраторы могут блокировать отдельные сообщения, которые неправильно печатаются в качестве нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="9fc86-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="9fc86-131">Дополнительные сведения см. [в материале Create blocked sender lists in EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9fc86-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="9fc86-132">Отправка ложных срабатыва-</span><span class="sxs-lookup"><span data-stu-id="9fc86-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="9fc86-133">Вместо использования следующих процедур для сообщения о ложных срабатываниях пользователи в Outlook и Outlook в Интернете могут использовать надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="9fc86-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="9fc86-134">Сведения об установке и использовании этих средств см. в добавлении [Enable the Report Message](enable-the-report-message-add-in.md) и Enable the Report [Phishing add-in.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9fc86-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="9fc86-135">Если сообщение было неправильно идентифицировано как нежелательное, вы можете отправить сообщение в команду анализа нежелательной почты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9fc86-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="9fc86-136">Аналитики оценят сообщение, и (в зависимости от результатов анализа) фильтры службы могут быть скорректированы, чтобы разрешить сообщение.</span><span class="sxs-lookup"><span data-stu-id="9fc86-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="9fc86-137">Создайте новое пустое сообщение электронной почты в `not_junk@office365.microsoft.com` качестве получателя.</span><span class="sxs-lookup"><span data-stu-id="9fc86-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="9fc86-138">Перетащите и сбросите неправильное сообщение в новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="9fc86-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="9fc86-139">Это позволит сохранить неправильное сообщение в качестве вложения в новом сообщении.</span><span class="sxs-lookup"><span data-stu-id="9fc86-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="9fc86-140">Не копируйте и не вдергируйте содержимое сообщения или переад. (нам нужно исходное сообщение, чтобы мы могли проверить заглавные книги сообщений).</span><span class="sxs-lookup"><span data-stu-id="9fc86-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="9fc86-141">В новом сообщении можно прикрепить несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="9fc86-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="9fc86-142">Убедитесь, что все сообщения одного типа: фишинговые или нежелательные сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="9fc86-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="9fc86-143">Оставьте текст нового сообщения пустым.</span><span class="sxs-lookup"><span data-stu-id="9fc86-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="9fc86-144">Используйте форматы .msg (формат Outlook по умолчанию) или .eml (Outlook в веб-формате) для подключенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="9fc86-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="9fc86-145">По завершению нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="9fc86-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="9fc86-146">Администраторы могут использовать несколько различных способов разрешить определенным сообщениям пропускать фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="9fc86-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="9fc86-147">Дополнительные сведения см. в [материале Create safe sender lists in EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9fc86-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="9fc86-148">Где хранятся данные из отправки в Microsoft?</span><span class="sxs-lookup"><span data-stu-id="9fc86-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="9fc86-149">Данные находятся в границе Office 365 соответствия требованиям в центрах обработки данных в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="9fc86-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="9fc86-150">Данные анализируют аналитики из инженерной группы, чтобы повысить эффективность фильтров.</span><span class="sxs-lookup"><span data-stu-id="9fc86-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="9fc86-151">Создайте правило потока почты для получения копий сообщений, которые сообщаются в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9fc86-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="9fc86-152">Инструкции см. в инструкции Использование правил потока [почты, чтобы узнать, какие пользователи сообщают в Корпорацию Майкрософт.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="9fc86-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
