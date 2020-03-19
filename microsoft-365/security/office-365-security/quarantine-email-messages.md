---
title: Карантин сообщений электронной почты в Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: В карантине Office 365 содержатся потенциально опасные или нежелательные сообщения. Администраторы и конечные пользователи могут получать доступ к карантину.
ms.openlocfilehash: 9c82ba9821c42fe6c3dd78dbcecf63327d176e93
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857313"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="ab655-104">Карантин в Office 365</span><span class="sxs-lookup"><span data-stu-id="ab655-104">Quarantine in Office 365</span></span>

<span data-ttu-id="ab655-105">Если вы являетесь клиентом Office 365 с почтовыми ящиками в Exchange Online или отдельном клиенте Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, можно использовать карантин для хранения потенциально опасных или нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab655-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="ab655-106">Политики защиты от вредоносных программ автоматически размещаются в карантине, если обнаружено *какое-либо* вложение, которое содержит вредоносную программу.</span><span class="sxs-lookup"><span data-stu-id="ab655-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="ab655-107">Дополнительные сведения см в разделе [Настройка политик защиты от вредоносных программ в Office 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab655-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="ab655-108">По умолчанию политики защиты от нежелательной почты размещаются в карантине и обеспечивают нежелательную почту и массовые сообщения электронной почты в папку нежелательной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab655-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="ab655-109">Кроме того, вы можете создавать и настраивать политики защиты от нежелательной почты для помещения нежелательной почты в карантин и массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ab655-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="ab655-110">Дополнительные сведения см в разделе [Настройка политик защиты от нежелательной почты в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab655-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ab655-111">Пользователи и администраторы могут работать с сообщениями, помещенными в карантин:</span><span class="sxs-lookup"><span data-stu-id="ab655-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="ab655-112">Администраторы могут работать со всеми типами сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="ab655-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="ab655-113">Только администраторы могут работать с сообщениями, помещенными в карантин, высокой вероятностью фишинга, или в результате правил для почтового процесса (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="ab655-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ab655-114">Дополнительные сведения см. [в статье Manage a карантинных сообщений и файлов в качестве администратора в Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ab655-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="ab655-115">Пользователи могут работать с сообщениями в карантине, где они являются получателями, если сообщение помещено в карантин в качестве нежелательной почты, массовых сообщений электронной почты или (на Апрель, 2020) фишинга.</span><span class="sxs-lookup"><span data-stu-id="ab655-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="ab655-116">Дополнительные сведения см. [в статье Поиск и освобождение сообщений, помещенных в карантин, в качестве пользователя в Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ab655-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="ab655-117">Чтобы запретить пользователям управлять своими сообщениями фишинга в карантине, администраторы могут настроить другое действие для фильтрации **фишинговых** сообщений вредоносности в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="ab655-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="ab655-118">Дополнительные сведения см в разделе [Настройка политик защиты от нежелательной почты в Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab655-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="ab655-119">Администраторы и пользователи могут сообщать о ложных срабатываниях в корпорацию Майкрософт в карантине.</span><span class="sxs-lookup"><span data-stu-id="ab655-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="ab655-120">Для получения дополнительных сведений о карантине обратитесь к разделу " [вопросы и ответы](quarantine-faq.md)".</span><span class="sxs-lookup"><span data-stu-id="ab655-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
