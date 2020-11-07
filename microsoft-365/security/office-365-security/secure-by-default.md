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
description: Узнайте, как найти и использовать отчеты по обеспечению безопасности электронной почты для вашей организации. Отчеты о безопасности электронной почты доступны в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944545"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="a54dc-104">Обеспечение безопасности по умолчанию в Office 365</span><span class="sxs-lookup"><span data-stu-id="a54dc-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a54dc-105">Термин "безопасность по умолчанию" используется для определения параметров по умолчанию, которые максимально безопасны.</span><span class="sxs-lookup"><span data-stu-id="a54dc-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="a54dc-106">Тем не менее, безопасность необходимо сбалансировать с производительностью.</span><span class="sxs-lookup"><span data-stu-id="a54dc-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="a54dc-107">Это может включать в себя балансировку:</span><span class="sxs-lookup"><span data-stu-id="a54dc-107">This can include balancing across:</span></span>
- <span data-ttu-id="a54dc-108">Удобство использования: параметры не должны возникать в способе повышения производительности пользователей.</span><span class="sxs-lookup"><span data-stu-id="a54dc-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="a54dc-109">Риск: безопасность может блокировать важные действия.</span><span class="sxs-lookup"><span data-stu-id="a54dc-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="a54dc-110">Устаревшие параметры: некоторые конфигурации для более ранних продуктов и компонентов могут потребоваться для бизнеса, даже если новые современные параметры улучшены.</span><span class="sxs-lookup"><span data-stu-id="a54dc-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="a54dc-111">Организации Microsoft 365 с почтовыми ящиками в Exchange Online защищаются с помощью Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a54dc-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a54dc-112">Эта защита включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="a54dc-112">This  protection includes:</span></span>
1. <span data-ttu-id="a54dc-113">Сообщения электронной почты с потенциальным вредоносным по будут автоматически помещены в карантин, а получатели будут уведомлены.</span><span class="sxs-lookup"><span data-stu-id="a54dc-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="a54dc-114">[В разделе Настройка политик защиты от вредоносных программ в EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a54dc-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="a54dc-115">Phishing-сообщения, отмеченные как "высокая степень доверия", будут обрабатываться в соответствии с действием политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a54dc-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="a54dc-116">[В разделе Настройка политик защиты от нежелательной почты в EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a54dc-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="a54dc-117">Так как корпорация Майкрософт хочет обеспечить безопасность наших клиентов по умолчанию, некоторые переопределения клиентов не применяются к вредоносным или высокодостоверным фишингом.</span><span class="sxs-lookup"><span data-stu-id="a54dc-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="a54dc-118">К этим переопределениям относятся:</span><span class="sxs-lookup"><span data-stu-id="a54dc-118">These overrides include:</span></span>
- <span data-ttu-id="a54dc-119">Списки разрешенных отправителей или список разрешенных доменов (политики защиты от нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="a54dc-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="a54dc-120">Надежные отправители Outlook</span><span class="sxs-lookup"><span data-stu-id="a54dc-120">Outlook Safe senders</span></span>
- <span data-ttu-id="a54dc-121">Белый список IP-адресов (фильтрация подключений)</span><span class="sxs-lookup"><span data-stu-id="a54dc-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="a54dc-122">Дополнительные сведения об этих переопределениях можно найти в подокне [Создание списков надежных отправителей](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="a54dc-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="a54dc-123">Обеспечение безопасности по умолчанию не является параметром, который может быть включен или отключен, но способ фильтрации в поле позволяет оставить потенциально опасные или нежелательные сообщения из почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="a54dc-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="a54dc-124">Фишинг и фишинг с высокой достоверностью отправляются в карантин.</span><span class="sxs-lookup"><span data-stu-id="a54dc-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="a54dc-125">Только администраторы могут управлять сообщениями, помещенными в карантин или фишингом с высокой достоверностью, а также сообщать корпорации Майкрософт о ложных срабатываниях.</span><span class="sxs-lookup"><span data-stu-id="a54dc-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="a54dc-126">Дополнительные сведения см в разделе [Manage a карантинных сообщений и файлов в качестве администратора в EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="a54dc-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="a54dc-127">Exceptions</span><span class="sxs-lookup"><span data-stu-id="a54dc-127">Exceptions</span></span>
<span data-ttu-id="a54dc-128">Единственными переопределениями, которые будут обходить все фильтры, являются:</span><span class="sxs-lookup"><span data-stu-id="a54dc-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="a54dc-129">Правила ETR/маил правил транспорта Exchange.</span><span class="sxs-lookup"><span data-stu-id="a54dc-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="a54dc-130">Установите уровень вероятности нежелательной почты (SCL) в сообщениях в EOP с помощью правил для почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="a54dc-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="a54dc-131">Список разрешений/блокировок клиентов: Управление URL-адресами и файлами в списке разрешенных и запрещенных клиентов.</span><span class="sxs-lookup"><span data-stu-id="a54dc-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="a54dc-132">Эти типы переопределений удобно использовать в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="a54dc-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="a54dc-133">Имитация фишинга: Имитация атак помогает определить уязвимых пользователей, прежде чем реальная атака повлияет на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="a54dc-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="a54dc-134">Security/Секопс почтовые ящики: выделенные почтовые ящики, используемые группами безопасности для получения нефильтруемых сообщений (хорошее и плохое).</span><span class="sxs-lookup"><span data-stu-id="a54dc-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="a54dc-135">Затем Teams может проверить, содержит ли они вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="a54dc-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="a54dc-136">Сторонние фильтры: некоторые сторонние производители рекомендуют отключить EOP (SCL =-1), так как сторонний фильтр будет управлять фильтрацией почты.</span><span class="sxs-lookup"><span data-stu-id="a54dc-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="a54dc-137">Корпорация Майкрософт не рекомендует отключать EOP, так как EOP является обязательным для защитника для Office 365.</span><span class="sxs-lookup"><span data-stu-id="a54dc-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="a54dc-138">Ложные срабатывания: вы можете разрешить некоторым сообщениям, которые по-прежнему анализируются корпорацией Майкрософт, с [помощью отправки администратором](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a54dc-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="a54dc-139">Как и во всех переопределениях, рекомендуется временно.</span><span class="sxs-lookup"><span data-stu-id="a54dc-139">As with all overrides, it is recommended that they are temporary.</span></span>
