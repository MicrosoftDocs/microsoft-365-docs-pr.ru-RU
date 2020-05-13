---
title: Сообщения электронной почты, помещенные в карантин
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о карантине в Exchange Online Protection (EOP), который содержит потенциально опасные или нежелательные сообщения.
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208286"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="47770-103">Сообщения электронной почты в карантине в EOP</span><span class="sxs-lookup"><span data-stu-id="47770-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="47770-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online можно использовать карантин для хранения потенциально опасных или нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="47770-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="47770-105">Политики защиты от вредоносных программ автоматически размещаются в карантине, если обнаружено *какое-либо* вложение, которое содержит вредоносную программу.</span><span class="sxs-lookup"><span data-stu-id="47770-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="47770-106">Для получения дополнительных сведений см. раздел [Настройка политик защиты от вредоносных программ в EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="47770-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="47770-107">По умолчанию политики защиты от нежелательной почты размещаются в карантине и обеспечивают нежелательную почту и массовые сообщения электронной почты в папку нежелательной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="47770-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="47770-108">Кроме того, вы можете создавать и настраивать политики защиты от нежелательной почты для помещения нежелательной почты в карантин и массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="47770-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="47770-109">Дополнительные сведения см. [в разделе Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="47770-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="47770-110">Пользователи и администраторы могут работать с сообщениями, помещенными в карантин:</span><span class="sxs-lookup"><span data-stu-id="47770-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="47770-111">Администраторы могут работать со всеми типами сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="47770-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="47770-112">Только администраторы могут работать с сообщениями, помещенными в карантин, высокой вероятностью фишинга, или в результате правил для почтового процесса (также называемых правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="47770-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="47770-113">Дополнительные сведения см. [в статье Manage a карантинных сообщений и файлов в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="47770-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="47770-114">Пользователи могут работать с сообщениями в карантине, где они являются получателями, если сообщение помещено в карантин в качестве нежелательной почты, массовых сообщений электронной почты или фишинга (на апрель 2020).</span><span class="sxs-lookup"><span data-stu-id="47770-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="47770-115">Дополнительные сведения см. [в статье Find and Release messages, помещенных в карантин, в качестве пользователя в EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="47770-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="47770-116">Чтобы запретить пользователям управлять своими сообщениями фишинга в карантине, администраторы могут настроить другое действие для фильтрации **фишинговых** сообщений вредоносности в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="47770-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="47770-117">Дополнительные сведения см. [в разделе Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="47770-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="47770-118">Администраторы и пользователи могут сообщать о ложных срабатываниях в корпорацию Майкрософт в карантине.</span><span class="sxs-lookup"><span data-stu-id="47770-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="47770-119">Для получения дополнительных сведений о карантине обратитесь к разделу " [вопросы и ответы](quarantine-faq.md)".</span><span class="sxs-lookup"><span data-stu-id="47770-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
