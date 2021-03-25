---
title: Карантин сообщений электронной почты
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
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205780"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="ab542-103">Карантин сообщений электронной почты в EOP</span><span class="sxs-lookup"><span data-stu-id="ab542-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ab542-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ab542-104">**Applies to**</span></span>
- [<span data-ttu-id="ab542-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ab542-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ab542-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ab542-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ab542-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab542-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ab542-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online карантин доступен для удержания потенциально опасных или нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ab542-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="ab542-109">Политики по борьбе с вредоносными программами автоматически карантином *сообщение,* если любое вложение установлено, содержит вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="ab542-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="ab542-110">Дополнительные сведения см. в [программе Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ab542-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="ab542-111">По умолчанию полиция по борьбе со спамом обеспечивает карантин фишинговых сообщений и доставляет спам и массовые сообщения электронной почты в папку нежелательной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="ab542-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="ab542-112">Но вы также можете создавать и настраивать политики по борьбе со спамом для карантиного спама и массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ab542-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="ab542-113">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab542-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ab542-114">Как пользователи, так и администраторы могут работать с карантинными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="ab542-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="ab542-115">Администраторы могут работать со всеми типами карантинов для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="ab542-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="ab542-116">Только администраторы могут работать с сообщениями, которые были на карантине в качестве вредоносных программ, фишинга с высокой уверенностью или в результате правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="ab542-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ab542-117">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ab542-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="ab542-118">Пользователи могут работать с карантинными сообщениями, в которых они являются получателем, если сообщение было на карантине в качестве спама, массовой электронной почты или (по апрель 2020 г.) фишинга.</span><span class="sxs-lookup"><span data-stu-id="ab542-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="ab542-119">Дополнительные сведения см. в [сообщении Find and release quarantined messages as a user in EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="ab542-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="ab542-120">Чтобы запретить пользователям управлять собственными фишинговыми сообщениями с карантином, администраторы  могут настроить другое действие для решения о фильтрации электронной почты фишинга в политиках по борьбе со спамом.</span><span class="sxs-lookup"><span data-stu-id="ab542-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="ab542-121">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ab542-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="ab542-122">Администраторы и пользователи могут сообщать о ложных срабатывающих в Microsoft на карантине.</span><span class="sxs-lookup"><span data-stu-id="ab542-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="ab542-123">Дополнительные сведения о карантине см. в [faq quarantine.](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="ab542-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
