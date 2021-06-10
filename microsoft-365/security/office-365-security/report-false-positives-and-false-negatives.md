---
title: Отчеты о ложных срабатываниях и ложных отрицаниях в Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Узнайте, как сообщать о ложных срабатывах и ложных Outlook с помощью функции Сообщение отчета.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789247"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="f4b04-103">Отчеты о ложных срабатываниях и ложных отрицаниях в Outlook</span><span class="sxs-lookup"><span data-stu-id="f4b04-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4b04-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f4b04-104">**Applies to**</span></span>
- [<span data-ttu-id="f4b04-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f4b04-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f4b04-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f4b04-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f4b04-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4b04-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f4b04-108">Если вы администратор в Microsoft 365 с Exchange Online почтовыми ящиками, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f4b04-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f4b04-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f4b04-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f4b04-110">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или на локальном почтовом ящике с помощью гибридной современной проверки подлинности можно отправить ложные срабатывания (хорошая электронная почта, которая была заблокирована или отправлена нежелательной папке) и ложные негативы (нежелательная электронная почта или фишинг, доставленные в почтовый ящик) в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f4b04-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4b04-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f4b04-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4b04-112">Для наилучшего использования пользовательской отправки используйте надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="f4b04-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f4b04-113">Встроенный интерфейс для сообщения о нежелательной или фишинговой информации в Outlook не может использовать политику [отправки пользователей.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f4b04-113">The built-in experience for reporting junk or phishing in Outlook can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="f4b04-114">Рекомендуется использовать надстройку "Сообщение отчетов" или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="f4b04-114">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

- <span data-ttu-id="f4b04-115">Надстройка сообщения отчетов и надстройка Report Phishing для Outlook на всех платформах (Outlook в Интернете, iOS, Android и Desktop).</span><span class="sxs-lookup"><span data-stu-id="f4b04-115">The the Report Message add-in and the Report Phishing add-in work for Outlook in all platforms (Outlook on the web, iOS, Android, and Desktop).</span></span>

- <span data-ttu-id="f4b04-116">Если вы администратор в организации с Exchange Online почтовыми ящиками, используйте портал Отправки в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="f4b04-116">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f4b04-117">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f4b04-117">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="f4b04-118">Вы можете настроить отправку сообщений непосредственно в Корпорацию Майкрософт, в почтовый ящик, который вы указываете, или оба.</span><span class="sxs-lookup"><span data-stu-id="f4b04-118">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="f4b04-119">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f4b04-119">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f4b04-120">Дополнительные сведения о том, как получить и включить надстройки Report Message или Report Phishing, см. в этой ссылке: Включить сообщение отчета или надстройки [для фишинга отчетов.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f4b04-120">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="f4b04-121">Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f4b04-121">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="f4b04-122">Использование функции сообщения отчета</span><span class="sxs-lookup"><span data-stu-id="f4b04-122">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="f4b04-123">Сообщение о нежелательных и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="f4b04-123">Report junk and phishing messages</span></span>

<span data-ttu-id="f4b04-124">Для сообщений в папке "Входящие" или любой другой папки электронной почты, кроме нежелательной почты, используйте следующий метод для сообщения о нежелательной почте и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="f4b04-124">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="f4b04-125">Выберите **эллипсы** Больше действий в правом верхнем углу выбранного сообщения, выберите сообщение **Report** из меню dropdown и выберите **нежелательное** или **фишинговое сообщение.**</span><span class="sxs-lookup"><span data-stu-id="f4b04-125">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   ![Сообщение отчетов — дополнительные действия](../../media/report-message-more-actions.png)
   
   ![Сообщение отчета — нежелательное и фишинговое сообщение](../../media/report-message-junk-phishing.png)

2. <span data-ttu-id="f4b04-128">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="f4b04-128">The selected messages will be sent to Microsoft for analysis and:</span></span>
   - <span data-ttu-id="f4b04-129">Перемещается в папку нежелательной почты, если сообщение о них сообщается как спам.</span><span class="sxs-lookup"><span data-stu-id="f4b04-129">Moved to the Junk Email folder if they were reported as spam.</span></span>
   - <span data-ttu-id="f4b04-130">Удаляется, если они были сообщения о фишинге.</span><span class="sxs-lookup"><span data-stu-id="f4b04-130">Deleted if they were reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="f4b04-131">Сообщения, которые не являются нежелательными</span><span class="sxs-lookup"><span data-stu-id="f4b04-131">Report messages that are not junk</span></span>

1. <span data-ttu-id="f4b04-132">Выберите **эллипсы** Больше действий в правом верхнем углу выбранного сообщения, выберите сообщение **Report** из меню dropdown и выберите **Not Junk**.</span><span class="sxs-lookup"><span data-stu-id="f4b04-132">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Not Junk**.</span></span>

   ![Сообщение отчетов — дополнительные действия](../../media/report-message-more-actions.png)
   
   ![Сообщение отчетов — не нежелательное](../../media/report-message-not-junk.png)

2. <span data-ttu-id="f4b04-135">Выбранное сообщение будет отправлено в Корпорацию Майкрософт для анализа и перемещено в папку "Входящие" или любую другую указанную папку.</span><span class="sxs-lookup"><span data-stu-id="f4b04-135">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="f4b04-136">Просмотр и просмотр сообщений, о чем сообщалось</span><span class="sxs-lookup"><span data-stu-id="f4b04-136">View and review reported messages</span></span>

<span data-ttu-id="f4b04-137">Чтобы просмотреть сообщения, которые пользователи сообщают в Корпорацию Майкрософт, у вас есть такие параметры:</span><span class="sxs-lookup"><span data-stu-id="f4b04-137">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="f4b04-138">Используйте портал Отправки администратора.</span><span class="sxs-lookup"><span data-stu-id="f4b04-138">Use the Admin Submissions portal.</span></span> <span data-ttu-id="f4b04-139">Дополнительные сведения см. в [материале Просмотр пользовательских представлений в Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f4b04-139">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>
- <span data-ttu-id="f4b04-140">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="f4b04-140">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="f4b04-141">Инструкции см. в инструкции Использование правил потока [почты, чтобы узнать, какие пользователи сообщают в Корпорацию Майкрософт.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f4b04-141">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
