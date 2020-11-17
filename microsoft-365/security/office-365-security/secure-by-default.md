---
title: Обеспечение безопасности по умолчанию в Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Дополнительные сведения о безопасности по умолчанию в Exchange Online Protection (EOP)
ms.openlocfilehash: d4345134e98ae204f73dfb51a0abf5136590a24c
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126665"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="d29ed-103">Обеспечение безопасности по умолчанию в Office 365</span><span class="sxs-lookup"><span data-stu-id="d29ed-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d29ed-104">Термин "безопасность по умолчанию" используется для определения параметров по умолчанию, которые максимально безопасны.</span><span class="sxs-lookup"><span data-stu-id="d29ed-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="d29ed-105">Тем не менее, безопасность необходимо сбалансировать с производительностью.</span><span class="sxs-lookup"><span data-stu-id="d29ed-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="d29ed-106">Это может включать в себя балансировку:</span><span class="sxs-lookup"><span data-stu-id="d29ed-106">This can include balancing across:</span></span>

- <span data-ttu-id="d29ed-107">Удобство использования: параметры не должны возникать в способе повышения производительности пользователей.</span><span class="sxs-lookup"><span data-stu-id="d29ed-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="d29ed-108">Риск: безопасность может блокировать важные действия.</span><span class="sxs-lookup"><span data-stu-id="d29ed-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="d29ed-109">Устаревшие параметры: некоторые конфигурации для более ранних продуктов и компонентов могут потребоваться для бизнеса, даже если новые современные параметры улучшены.</span><span class="sxs-lookup"><span data-stu-id="d29ed-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="d29ed-110">Организации Microsoft 365 с почтовыми ящиками в Exchange Online защищаются с помощью Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d29ed-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d29ed-111">Эта защита включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="d29ed-111">This protection includes:</span></span>

1. <span data-ttu-id="d29ed-112">Сообщения электронной почты с потенциальным вредоносным по будут автоматически помещены в карантин, а получатели будут уведомлены.</span><span class="sxs-lookup"><span data-stu-id="d29ed-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="d29ed-113">[В разделе Настройка политик защиты от вредоносных программ в EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="d29ed-114">Phishing-сообщения, отмеченные как "высокая степень доверия", будут обрабатываться в соответствии с действием политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d29ed-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="d29ed-115">[В разделе Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d29ed-116">Так как корпорация Майкрософт хочет обеспечить безопасность наших клиентов по умолчанию, некоторые переопределения клиентов не применяются к вредоносным или высокодостоверным фишингом.</span><span class="sxs-lookup"><span data-stu-id="d29ed-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="d29ed-117">К этим переопределениям относятся:</span><span class="sxs-lookup"><span data-stu-id="d29ed-117">These overrides include:</span></span>

- <span data-ttu-id="d29ed-118">Списки разрешенных отправителей или список разрешенных доменов (политики защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="d29ed-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="d29ed-119">Надежные отправители Outlook</span><span class="sxs-lookup"><span data-stu-id="d29ed-119">Outlook Safe senders</span></span>
- <span data-ttu-id="d29ed-120">Белый список IP-адресов (фильтрация подключений)</span><span class="sxs-lookup"><span data-stu-id="d29ed-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="d29ed-121">Дополнительные сведения об этих переопределениях можно найти в подокне [Создание списков надежных отправителей](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="d29ed-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="d29ed-122">Обеспечение безопасности по умолчанию не является параметром, который может быть включен или отключен, но способ фильтрации в поле позволяет оставить потенциально опасные или нежелательные сообщения из почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="d29ed-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="d29ed-123">Фишинг и фишинг с высокой достоверностью отправляются в карантин.</span><span class="sxs-lookup"><span data-stu-id="d29ed-123">Malware and high confidence phishing should be sent to quarantine.</span></span> <span data-ttu-id="d29ed-124">Только администраторы могут управлять сообщениями, помещенными в карантин или фишингом с высокой достоверностью, а также сообщать корпорации Майкрософт о ложных срабатываниях.</span><span class="sxs-lookup"><span data-stu-id="d29ed-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="d29ed-125">Дополнительные сведения см в разделе [Manage a карантинных сообщений и файлов в качестве администратора в EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="d29ed-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="d29ed-126">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d29ed-126">Exceptions</span></span>

<span data-ttu-id="d29ed-127">Единственным переопределением, позволяющим обходить сообщения с фишингом с высоким уровнем достоверности, являются правила обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="d29ed-127">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d29ed-128">Чтобы обойти фильтрацию с помощью правил для почтового процесса, ознакомьтесь со статьей [Использование правил для обработки почты для установки НЕжелательной почты в сообщениях](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-128">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="d29ed-129">Переопределения следует использовать только для:</span><span class="sxs-lookup"><span data-stu-id="d29ed-129">Overrides should only be used for:</span></span>

- <span data-ttu-id="d29ed-130">Имитация фишинга: Имитация атак помогает определить уязвимых пользователей, прежде чем реальная атака повлияет на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="d29ed-130">Phishing simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="d29ed-131">Security/Секопс почтовые ящики: выделенные почтовые ящики, используемые группами безопасности для получения нефильтруемых сообщений (хорошее и плохое).</span><span class="sxs-lookup"><span data-stu-id="d29ed-131">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="d29ed-132">Затем Teams может проверить, содержит ли они вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="d29ed-132">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="d29ed-133">Сторонние фильтры: некоторые сторонние производители рекомендуют отключить EOP (SCL =-1), так как сторонний фильтр будет управлять фильтрацией почты.</span><span class="sxs-lookup"><span data-stu-id="d29ed-133">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="d29ed-134">Корпорация Майкрософт не рекомендует отключать EOP, так как EOP является обязательным для защитника для Office 365.</span><span class="sxs-lookup"><span data-stu-id="d29ed-134">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="d29ed-135">Ложные срабатывания: вы можете разрешить некоторым сообщениям, которые по-прежнему анализируются корпорацией Майкрософт, с [помощью отправки администратором](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="d29ed-135">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="d29ed-136">Как и во всех переопределениях, рекомендуется временно.</span><span class="sxs-lookup"><span data-stu-id="d29ed-136">As with all overrides, it is recommended that they are temporary.</span></span>
