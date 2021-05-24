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
ms.openlocfilehash: 6f8c4fc327bfd467cdd1d0043c454e222e84125c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625117"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="3603b-103">Отчеты о ложных срабатываниях и ложных отрицаниях в Outlook</span><span class="sxs-lookup"><span data-stu-id="3603b-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3603b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="3603b-104">**Applies to**</span></span>
- [<span data-ttu-id="3603b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3603b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3603b-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="3603b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3603b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3603b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="3603b-108">Если вы администратор в Microsoft 365 с Exchange Online почтовыми ящиками, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3603b-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3603b-109">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3603b-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="3603b-110">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или на локальном почтовом ящике с помощью гибридной современной проверки подлинности можно отправить ложные срабатывания (хорошая электронная почта, которая была заблокирована или отправлена нежелательной папке) и ложные негативы (нежелательная электронная почта или фишинг, доставленные в почтовый ящик) в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="3603b-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3603b-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="3603b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3603b-112">Для наилучшего использования пользовательской отправки используйте надстройку Report Message или надстройку Report Phishing.</span><span class="sxs-lookup"><span data-stu-id="3603b-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="3603b-113">Обратите внимание, что эта надстройка работает Outlook на всех платформах: в Интернете, iOS, Android и Desktop.</span><span class="sxs-lookup"><span data-stu-id="3603b-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="3603b-114">Если вы администратор в организации с Exchange Online почтовыми ящиками, используйте портал Отправки в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="3603b-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3603b-115">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3603b-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="3603b-116">Вы можете настроить отправку сообщений непосредственно в Корпорацию Майкрософт, в почтовый ящик, который вы указываете, или оба.</span><span class="sxs-lookup"><span data-stu-id="3603b-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="3603b-117">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3603b-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="3603b-118">Дополнительные сведения о том, как получить и включить надстройки Report Message или Report Phishing, см. в этой ссылке: Включить сообщение отчета или надстройки [для фишинга отчетов.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="3603b-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="3603b-119">Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3603b-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="3603b-120">Использование функции сообщения отчета</span><span class="sxs-lookup"><span data-stu-id="3603b-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="3603b-121">Сообщение о нежелательных и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="3603b-121">Report junk and phishing messages</span></span>

<span data-ttu-id="3603b-122">Для сообщений в папке "Входящие" или любой другой папки электронной почты, кроме нежелательной почты, используйте следующий метод для сообщения о нежелательной почте и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="3603b-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="3603b-123">Щелкните **эллипсы** Больше действий в правом верхнем углу выбранного сообщения, щелкните сообщение **Отчет** из выпадаемого меню, а затем выберите **нежелательное** или **фишинговое** сообщение.</span><span class="sxs-lookup"><span data-stu-id="3603b-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3603b-124">![Сообщение отчетов — дополнительные действия](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="3603b-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3603b-125">![Сообщение отчета — нежелательное и фишинговое сообщение](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="3603b-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="3603b-126">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="3603b-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="3603b-127">Перемещается в папку нежелательной почты, если сообщение о ней сообщается как спам.</span><span class="sxs-lookup"><span data-stu-id="3603b-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="3603b-128">Удаляется, если оно было отчитано как фишинг.</span><span class="sxs-lookup"><span data-stu-id="3603b-128">Deleted if it was reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="3603b-129">Сообщения, которые не являются нежелательными</span><span class="sxs-lookup"><span data-stu-id="3603b-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="3603b-130">Щелкните **эллипсы** Больше действий в правом верхнем углу выбранного сообщения, щелкните сообщение **Отчет** из выпадаемого меню, а затем нажмите **кнопку Не нежелательной**.</span><span class="sxs-lookup"><span data-stu-id="3603b-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3603b-131">![Сообщение отчетов — дополнительные действия](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="3603b-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3603b-132">![Сообщение отчетов — не нежелательное](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="3603b-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="3603b-133">Выбранное сообщение будет отправлено в Корпорацию Майкрософт для анализа и перемещено в папку "Входящие" или любую другую указанную папку.</span><span class="sxs-lookup"><span data-stu-id="3603b-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="3603b-134">Просмотр и просмотр сообщений, о чем сообщалось</span><span class="sxs-lookup"><span data-stu-id="3603b-134">View and review reported messages</span></span>

<span data-ttu-id="3603b-135">Чтобы просмотреть сообщения, которые пользователи сообщают в Корпорацию Майкрософт, у вас есть такие параметры:</span><span class="sxs-lookup"><span data-stu-id="3603b-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="3603b-136">Используйте портал Отправки администратора.</span><span class="sxs-lookup"><span data-stu-id="3603b-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="3603b-137">Дополнительные сведения см. в [материале Просмотр пользовательских представлений в Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="3603b-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="3603b-138">Создайте правило потока почты (также известное как правило транспорта) для отправки копий сообщений.</span><span class="sxs-lookup"><span data-stu-id="3603b-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="3603b-139">Инструкции см. в инструкции Использование правил потока [почты, чтобы узнать, какие пользователи сообщают в Корпорацию Майкрософт.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="3603b-139">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
