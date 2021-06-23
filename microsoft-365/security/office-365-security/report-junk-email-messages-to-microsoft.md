---
title: Сообщение о спаме, не спаме и фишинговых сообщениях в Корпорации Майкрософт
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о различных способах отчета о хороших и плохих сообщениях и файлах в Корпорации Майкрософт для анализа.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082820"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="3682b-103">Передача информации о сообщениях и файлах в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3682b-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3682b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="3682b-104">**Applies to**</span></span>
- [<span data-ttu-id="3682b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3682b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3682b-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="3682b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3682b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3682b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3682b-108">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков, как пользователи, так и администраторы имеют несколько различных методов для отправки сообщений электронной почты и файлов в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3682b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="3682b-109">Метод</span><span class="sxs-lookup"><span data-stu-id="3682b-109">Method</span></span>|<span data-ttu-id="3682b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3682b-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="3682b-111">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3682b-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="3682b-112">Рекомендуемый метод отчетности для администраторов в организациях с Exchange Online почтовыми ящиками (недоступны в автономных EOP).</span><span class="sxs-lookup"><span data-stu-id="3682b-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="3682b-113">Включить сообщение отчета или надстройки для фишинга отчетов</span><span class="sxs-lookup"><span data-stu-id="3682b-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="3682b-114">Работает с Outlook и Outlook в Интернете (ранее известный как Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="3682b-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="3682b-115">В зависимости от вашей подписки сообщения, о которых пользователи сообщали с надстройкими, доступны на портале [Представления](admin-submission.md)администратора, результатах автоматического расследования и ответа [(AIR),](air-view-investigation-results.md)отчете о сообщениях пользователя и [](view-email-security-reports.md#user-reported-messages-report) [проводнике.](threat-explorer-views.md#email--submissions)</span><span class="sxs-lookup"><span data-stu-id="3682b-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="3682b-116">Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан.</span><span class="sxs-lookup"><span data-stu-id="3682b-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="3682b-117">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3682b-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="3682b-118">Отчеты о ложных срабатываниях и ложных отрицаниях в Outlook</span><span class="sxs-lookup"><span data-stu-id="3682b-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="3682b-119">Отправка ложных срабатываний (хорошая электронная почта, которая была заблокирована или отправлена нежелательной папке) и ложных негативов (нежелательных сообщений электронной почты или фишинга, которые были доставлены в почтовый ящик) в Exchange Online Protection (EOP) с помощью функции Сообщение отчетов.</span><span class="sxs-lookup"><span data-stu-id="3682b-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="3682b-120">Вручную отправлять сообщения в Корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="3682b-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="3682b-121">Вручную отправлять прикрепленные сообщения на конкретные адреса электронной почты Майкрософт для спама, а не нежелательной почты и фишинга.</span><span class="sxs-lookup"><span data-stu-id="3682b-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="3682b-122">Использование правил потока почты для просмотра отчетов, передаваемых пользователями в Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3682b-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="3682b-123">Узнайте, как создать правило потока почты (также известное как правило транспорта), которое сообщает вам, когда пользователи сообщают сообщения в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="3682b-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="3682b-124">Отправка вредоносных программ и не вредоносных программ в Корпорацию Майкрософт для анализа</span><span class="sxs-lookup"><span data-stu-id="3682b-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="3682b-125">Используйте сайт портал для обнаружения угроз (Microsoft) для отправки вложений и других файлов.</span><span class="sxs-lookup"><span data-stu-id="3682b-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="3682b-126">Если сообщения спама или фишинга были поставлены на карантин, а не доставлены, пользователи могут сообщить об этих сообщениях в Корпорацию Майкрософт из карантина на Microsoft 365 Defender портале.</span><span class="sxs-lookup"><span data-stu-id="3682b-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="3682b-127">Подробные сведения см. в материале [Find and release quarantined messages as a user in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="3682b-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3682b-128">Данные из представлений в Корпорацию Майкрософт находятся в Office 365 соответствия требованиям в центрах обработки данных в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="3682b-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="3682b-129">Данные анализируют аналитики из инженерной группы, чтобы повысить эффективность фильтров.</span><span class="sxs-lookup"><span data-stu-id="3682b-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
