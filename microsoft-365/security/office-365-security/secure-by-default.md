---
title: Защита по умолчанию в Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Узнайте больше о параметре безопасности по умолчанию в Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8af609b8ed50b0bfacb7d9f5397fab4c4726927
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040548"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="d050f-103">Защита по умолчанию в Office 365</span><span class="sxs-lookup"><span data-stu-id="d050f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d050f-104">"Защита по умолчанию" — это термин, используемый для определения наиболее безопасных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d050f-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="d050f-105">Однако безопасность должна быть сбалансирована с производительностью.</span><span class="sxs-lookup"><span data-stu-id="d050f-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="d050f-106">Это может включать балансировку между:</span><span class="sxs-lookup"><span data-stu-id="d050f-106">This can include balancing across:</span></span>

- <span data-ttu-id="d050f-107">**Usability**: Settings should not get in the way of user productivity.</span><span class="sxs-lookup"><span data-stu-id="d050f-107">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="d050f-108">**Риск:** безопасность может блокировать важные действия.</span><span class="sxs-lookup"><span data-stu-id="d050f-108">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="d050f-109">**Устаревшие параметры:** некоторые конфигурации старых продуктов и функций могут потребоваться поддерживать по коммерческим причинам, даже если улучшены новые, современные параметры.</span><span class="sxs-lookup"><span data-stu-id="d050f-109">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="d050f-110">Организации Microsoft 365 с почтовыми ящиками в Exchange Online защищены службой Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d050f-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d050f-111">Эта защита включает в себя:</span><span class="sxs-lookup"><span data-stu-id="d050f-111">This protection includes:</span></span>

- <span data-ttu-id="d050f-112">Сообщения электронной почты с подозрительными вредоносными программами автоматически будут отправлены на карантин, а получатели будут уведомлены.</span><span class="sxs-lookup"><span data-stu-id="d050f-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="d050f-113">См. ["Настройка политик борьбы с вредоносными программами" в EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="d050f-114">Сообщения электронной почты, идентифицированные как фишинговые сообщения с высокой достоверности, будут обрабатываться в соответствии с действием политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d050f-114">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="d050f-115">См. ["Настройка политик борьбы с нежелательной почтой" в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d050f-116">Дополнительные сведения об EOP см. в [обзоре Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-116">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="d050f-117">Так как корпорация Майкрософт хочет обеспечить безопасность наших клиентов по умолчанию, некоторые переопределения клиентов не применяются к вредоносным программам или фишингу с высокой достоверности.</span><span class="sxs-lookup"><span data-stu-id="d050f-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="d050f-118">К этим переопределениям относятся:</span><span class="sxs-lookup"><span data-stu-id="d050f-118">These overrides include:</span></span>

- <span data-ttu-id="d050f-119">Списки разрешенных отправников или списки разрешенных доменов (политики нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="d050f-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="d050f-120">Надежные отправитые в Outlook</span><span class="sxs-lookup"><span data-stu-id="d050f-120">Outlook Safe Senders</span></span>
- <span data-ttu-id="d050f-121">Список ip-адресов (фильтрация подключений)</span><span class="sxs-lookup"><span data-stu-id="d050f-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="d050f-122">Дополнительные сведения об этих переопределениях можно найти в списке ["Создание надежных отправитель".](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-122">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d050f-123">We're in the process of deprecating the **Move message to Junk Email folder** action for a High confidence **phishing email** verdict in EOP anti-spam policies.</span><span class="sxs-lookup"><span data-stu-id="d050f-123">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="d050f-124">Политики защиты от нежелательной почты, которые используют это действие для фишинговых сообщений с высокой достоверности, будут преобразованы в сообщение **карантина.**</span><span class="sxs-lookup"><span data-stu-id="d050f-124">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="d050f-125">Действие **"Перенаправление сообщения на адрес электронной** почты" для фишинговых сообщений с высокой достоверности не влияет.</span><span class="sxs-lookup"><span data-stu-id="d050f-125">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="d050f-126">Защита по умолчанию не является параметром, который можно отключить или отключить, но обеспечивает защиту от потенциально опасных или нежелательных сообщений из ваших почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="d050f-126">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="d050f-127">Фишинговые сообщения с высокой достоверности и вредоносные программы должны быть на карантине.</span><span class="sxs-lookup"><span data-stu-id="d050f-127">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="d050f-128">Только администраторы могут управлять сообщениями, которые находятся на карантине как вредоносные программы или фишинговые сообщения с высокой достоверности, а также сообщать о ложных срабатываниях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d050f-128">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="d050f-129">Дополнительные сведения см. в под управлением сообщений и файлов на карантине от имени [администратора в EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-129">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="d050f-130">Подробнее о том, почему мы это делаем</span><span class="sxs-lookup"><span data-stu-id="d050f-130">More on why we're doing this</span></span>

<span data-ttu-id="d050f-131">Безопасность по умолчанию зависит от того, что мы выполнят те же действия с сообщением, что и если вы знаете, что сообщение вредоносное, даже если настроенное исключение позволит доставить сообщение в противном случае.</span><span class="sxs-lookup"><span data-stu-id="d050f-131">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="d050f-132">Это тот же подход, который мы всегда использовали для вредоносных программ, и теперь мы расширяем это поведение до фишинговых сообщений с высокой достоверности.</span><span class="sxs-lookup"><span data-stu-id="d050f-132">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="d050f-133">Наши данные указывают, что пользователь в 30 раз чаще щелкает вредоносную ссылку в сообщениях в папке нежелательной почты или в карантине.</span><span class="sxs-lookup"><span data-stu-id="d050f-133">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="d050f-134">Наши данные также указывают, что коэффициент ложного срабатывания (хорошие сообщения помечены как плохое) для фишинговых сообщений с высокой достоверности очень низкий, и администраторы могут разрешать любые ложные срабатывания с помощью отправленных администратором сообщений.</span><span class="sxs-lookup"><span data-stu-id="d050f-134">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="d050f-135">Мы также определили, что списки разрешенных отправителей и разрешенных доменов в политиках борьбы с нежелательной почтой и надежных отправителей в Outlook слишком обширны и причиняют больше вреда, чем пользы.</span><span class="sxs-lookup"><span data-stu-id="d050f-135">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="d050f-136">Другими словами, мы действуем от вашего имени, чтобы предотвратить скомпрометирование пользователей.</span><span class="sxs-lookup"><span data-stu-id="d050f-136">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="d050f-137">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d050f-137">Exceptions</span></span>

<span data-ttu-id="d050f-138">Единственное переопределение, которое позволяет сообщению с высокой достоверности обходить фильтрацию, — это правила потока почты Exchange (также известные как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="d050f-138">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d050f-139">Чтобы использовать правила потока почты для обхода фильтрации, см. "Использование правил потока почты для применения [SCL в сообщениях".](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-139">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="d050f-140">Переопределения следует использовать только в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="d050f-140">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="d050f-141">Имитации фишинга: имитированные атаки могут помочь вам определить уязвимых пользователей до того, как реальные атаки понвяют вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="d050f-141">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="d050f-142">Почтовые ящики безопасности и secOps: выделенные почтовые ящики, используемые группами безопасности для получения неотобраченных сообщений (как хороший, так и плохой).</span><span class="sxs-lookup"><span data-stu-id="d050f-142">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="d050f-143">Затем Teams может просмотреть, содержат ли они вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="d050f-143">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="d050f-144">Сторонние фильтры: защита по умолчанию не применяется, если запись MX домена не относится к Office 365.</span><span class="sxs-lookup"><span data-stu-id="d050f-144">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="d050f-145">Ложные срабатываия: может потребоваться временно разрешить определенные сообщения, которые по-прежнему анализируются корпорацией Майкрософт, с помощью от [отправленных администратором сообщений.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d050f-145">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="d050f-146">Как и во всех переопределениях, рекомендуется, чтобы они были временными.</span><span class="sxs-lookup"><span data-stu-id="d050f-146">As with all overrides, it is recommended that they are temporary.</span></span>
