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
ms.service: O365-seccomp
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
ms.openlocfilehash: 8a978ece029de06bcb7b434de730b0baea33a5e1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794332"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="c85aa-103">Сообщения электронной почты, отправленные на карантин в EOP</span><span class="sxs-lookup"><span data-stu-id="c85aa-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c85aa-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online карантин доступен для удержания потенциально опасных или нежелательных сообщений.</span><span class="sxs-lookup"><span data-stu-id="c85aa-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="c85aa-105">Политики для борьбы с вредоносными программами  автоматически заключяют сообщение в карантин, если обнаружено, что любое вложение содержит вредоносную программу.</span><span class="sxs-lookup"><span data-stu-id="c85aa-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="c85aa-106">Дополнительные сведения см. в подстройке "Настройка политик борьбы с [вредоносными программами" в EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c85aa-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="c85aa-107">По умолчанию для защиты от нежелательной почты в карантине доставляются нежелательные и массовые сообщения в папку нежелательной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="c85aa-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="c85aa-108">Однако вы также можете создать и настроить политики нежелательной почты для карантина нежелательной почты и массовых сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c85aa-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="c85aa-109">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c85aa-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c85aa-110">Как пользователи, так и администраторы могут работать с сообщениями в карантине:</span><span class="sxs-lookup"><span data-stu-id="c85aa-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="c85aa-111">Администраторы могут работать со всеми типами сообщений в карантине для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="c85aa-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="c85aa-112">Только администраторы могут работать с сообщениями, которые были отправлены на карантин как вредоносные программы, фишинг с высокой достоверности или в результате правил потока почты (также известных как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="c85aa-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c85aa-113">Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="c85aa-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="c85aa-114">Пользователи могут работать с сообщениями, отправленными на карантин, если они были отправлены на карантин как спам, массовая рассылка или (в апреле 2020 г.) фишинг.</span><span class="sxs-lookup"><span data-stu-id="c85aa-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="c85aa-115">Дополнительные сведения см. в записи поиска и освобождения сообщений на карантине от пользователя [в EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="c85aa-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="c85aa-116">Чтобы запретить пользователям управлять собственными фишинговыми сообщениями, отправленными на карантин,  администраторы могут настроить другое действие для решения фильтрации фишинговых сообщений в политиках защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c85aa-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c85aa-117">Дополнительные сведения см. в статье [Настройка политик защиты от спама в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c85aa-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="c85aa-118">Администраторы и пользователи могут сообщать о ложных срабатывающих сообщениях корпорации Майкрософт в карантине.</span><span class="sxs-lookup"><span data-stu-id="c85aa-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="c85aa-119">Дополнительные сведения о карантине см. в под вопросе ["Quarantine FAQ" (Quarantine FAQ).](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="c85aa-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
