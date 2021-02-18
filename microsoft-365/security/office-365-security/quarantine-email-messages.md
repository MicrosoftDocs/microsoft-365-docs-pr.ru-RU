---
title: Сообщения электронной почты, отправленные на карантин
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о карантине в Exchange Online Protection (EOP), который содержит потенциально опасные или нежелательные сообщения.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288769"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="86a9f-103">Сообщения электронной почты, отправленные на карантин в EOP</span><span class="sxs-lookup"><span data-stu-id="86a9f-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="86a9f-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="86a9f-104">**Applies to**</span></span>
- [<span data-ttu-id="86a9f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="86a9f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="86a9f-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="86a9f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="86a9f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86a9f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="86a9f-108">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online карантин доступен для удержания потенциально опасных или нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="86a9f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="86a9f-109">Политики для борьбы с вредоносными программами  автоматически заключяют сообщение в карантин, если обнаружено, что любое вложение содержит вредоносную программу.</span><span class="sxs-lookup"><span data-stu-id="86a9f-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="86a9f-110">Дополнительные сведения см. в подстройке "Настройка политик для борьбы с [вредоносными программами" в EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="86a9f-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="86a9f-111">По умолчанию для защиты от нежелательной почты в карантине доставляются нежелательные и массовые сообщения в папку нежелательной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="86a9f-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="86a9f-112">Однако вы также можете создавать и настраивать политики нежелательной почты для карантина нежелательной почты и массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="86a9f-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="86a9f-113">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="86a9f-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="86a9f-114">Как пользователи, так и администраторы могут работать с сообщениями в карантине:</span><span class="sxs-lookup"><span data-stu-id="86a9f-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="86a9f-115">Администраторы могут работать со всеми типами сообщений в карантине для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="86a9f-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="86a9f-116">Только администраторы могут работать с сообщениями, которые были отправлены на карантин как вредоносные программы, фишинг с высокой достоверности или в результате правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="86a9f-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="86a9f-117">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="86a9f-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="86a9f-118">Пользователи могут работать с сообщениями, отправленными на карантин, если они были отправлены на карантин как спам, массовая рассылка или (в апреле 2020 г.) фишинг.</span><span class="sxs-lookup"><span data-stu-id="86a9f-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="86a9f-119">Дополнительные сведения см. в записи поиска и освобождения сообщений на карантине от пользователя [в EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="86a9f-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="86a9f-120">Чтобы запретить пользователям управлять собственными фишинговыми сообщениями, отправленными на карантин,  администраторы могут настроить другое действие для решения фильтрации фишинговых сообщений в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="86a9f-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="86a9f-121">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="86a9f-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="86a9f-122">Администраторы и пользователи могут сообщать о ложных срабатывах в майкрософт в карантине.</span><span class="sxs-lookup"><span data-stu-id="86a9f-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="86a9f-123">Дополнительные сведения о карантине см. в под вопросе ["Quarantine FAQ" (Quarantine FAQ).](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="86a9f-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
