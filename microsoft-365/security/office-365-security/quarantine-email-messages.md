---
title: Сообщения электронной почты в карантине
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
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
description: Администраторы могут узнать о карантине в Exchange Online Protection (EOP), в котором есть потенциально опасные или нежелательные сообщения.
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826805"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="eaac4-103">Сообщения электронной почты, помещенные в карантин в EOP</span><span class="sxs-lookup"><span data-stu-id="eaac4-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="eaac4-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online карантин может содержать потенциально опасные или нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="eaac4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="eaac4-105">Политики защиты от вредоносных программ автоматически помещают сообщение на карантин, если *в наличии* вложения обнаружены вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="eaac4-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="eaac4-106">Дополнительные сведения см. в статье ["Настройка политик защиты от вредоносных программ" в EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="eaac4-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="eaac4-107">По умолчанию политики защиты от нежелательной почты, отправляющие в карантин фишинговые сообщения, а также доставку нежелательной почты и массовых сообщений в папку "Нежелательная почта" пользователя.</span><span class="sxs-lookup"><span data-stu-id="eaac4-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="eaac4-108">Однако вы также можете создавать и настраивать политики защиты от нежелательной почты для помещения нежелательных сообщений и массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="eaac4-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="eaac4-109">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="eaac4-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="eaac4-110">Как пользователи, так и администраторы могут работать с сообщениями, помещенные на карантин:</span><span class="sxs-lookup"><span data-stu-id="eaac4-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="eaac4-111">Администраторы могут работать со всеми типами сообщений, помещенных в карантин, для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="eaac4-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="eaac4-112">Только администраторы могут работать с сообщениями, помещенными в карантин как вредоносные программы, фишинг с высоким уровнем вероятности или в результате правил потока обработки почты (правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="eaac4-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="eaac4-113">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="eaac4-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="eaac4-114">Пользователи могут работать с сообщениями, помещенными в карантин, если они являются спамом, массовой рассылкой или (по достижении апреля 2020 года) фишинг.</span><span class="sxs-lookup"><span data-stu-id="eaac4-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="eaac4-115">Дополнительные сведения см. в статье "Поиск [и освобождение сообщений на карантине для пользователя в EOP".](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="eaac4-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="eaac4-116">Чтобы запретить пользователям управлять собственными фишинговыми сообщениями, помещенными в карантин, администраторы могут настроить другое действие для заявления о фильтрации фишинговых сообщений, заключаемых в политиках защиты от нежелательной почты. **Phishing email**</span><span class="sxs-lookup"><span data-stu-id="eaac4-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="eaac4-117">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="eaac4-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="eaac4-118">Администраторы и пользователи могут сообщать о ложных срабатываниях в майкрософт в карантине.</span><span class="sxs-lookup"><span data-stu-id="eaac4-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="eaac4-119">Дополнительные сведения о карантине см. в разделе ["Вопросы и ответы, посвященные карантину".](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="eaac4-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
