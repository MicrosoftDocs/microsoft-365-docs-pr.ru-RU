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
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288517"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="641f2-103">Защита по умолчанию в Office 365</span><span class="sxs-lookup"><span data-stu-id="641f2-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="641f2-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="641f2-104">**Applies to**</span></span>
- [<span data-ttu-id="641f2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="641f2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="641f2-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="641f2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="641f2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="641f2-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="641f2-108">Термин "Защита по умолчанию" используется для определения наиболее безопасных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="641f2-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="641f2-109">Однако безопасность должна быть сбалансирована с производительностью.</span><span class="sxs-lookup"><span data-stu-id="641f2-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="641f2-110">Это может включать балансировку между:</span><span class="sxs-lookup"><span data-stu-id="641f2-110">This can include balancing across:</span></span>

- <span data-ttu-id="641f2-111">**Usability**: Settings should not get in the way of user productivity.</span><span class="sxs-lookup"><span data-stu-id="641f2-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="641f2-112">**Риск:** безопасность может блокировать важные действия.</span><span class="sxs-lookup"><span data-stu-id="641f2-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="641f2-113">**Устаревшие параметры:** некоторые конфигурации старых продуктов и функций могут потребоваться поддерживать по коммерческим причинам, даже если улучшены новые, современные параметры.</span><span class="sxs-lookup"><span data-stu-id="641f2-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="641f2-114">Организации Microsoft 365 с почтовыми ящиками в Exchange Online защищены службой Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="641f2-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="641f2-115">Эта защита включает в себя:</span><span class="sxs-lookup"><span data-stu-id="641f2-115">This protection includes:</span></span>

- <span data-ttu-id="641f2-116">Электронная почта с подозрительными вредоносными программами автоматически будет отправлена на карантин, а получатели будут уведомлены.</span><span class="sxs-lookup"><span data-stu-id="641f2-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="641f2-117">См. ["Настройка политик борьбы с вредоносными программами" в EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="641f2-118">Сообщения электронной почты, идентифицированные как фишинговые сообщения с высокой достоверности, будут обрабатываться в соответствии с действием политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="641f2-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="641f2-119">См. ["Настройка политик борьбы с нежелательной почтой" в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="641f2-120">Дополнительные сведения об EOP см. в [обзоре Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="641f2-121">Так как корпорация Майкрософт хочет обеспечить безопасность наших клиентов по умолчанию, некоторые переопределения клиентов не применяются к вредоносным программам или фишингу с высокой достоверности.</span><span class="sxs-lookup"><span data-stu-id="641f2-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="641f2-122">К этим переопределениям относятся:</span><span class="sxs-lookup"><span data-stu-id="641f2-122">These overrides include:</span></span>

- <span data-ttu-id="641f2-123">Списки разрешенных отправитель или разрешенные списки доменов (политики нежелательной почты)</span><span class="sxs-lookup"><span data-stu-id="641f2-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="641f2-124">Надежные отправитые в Outlook</span><span class="sxs-lookup"><span data-stu-id="641f2-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="641f2-125">Список ip-адресов (фильтрация подключений)</span><span class="sxs-lookup"><span data-stu-id="641f2-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="641f2-126">Дополнительные сведения об этих переопределениях можно найти в списке ["Создание безопасных отправитель".](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="641f2-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a High confidence **phishing email** verdict in EOP anti-spam policies.</span><span class="sxs-lookup"><span data-stu-id="641f2-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="641f2-128">Политики защиты от нежелательной почты, которые используют это действие для фишинговых сообщений с высокой достоверности, будут преобразованы в сообщение **карантина.**</span><span class="sxs-lookup"><span data-stu-id="641f2-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="641f2-129">Сообщение **перенаправления на адрес электронной** почты для фишинговых сообщений с высокой достоверности не влияет.</span><span class="sxs-lookup"><span data-stu-id="641f2-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="641f2-130">Защита по умолчанию не является параметром, который можно отключить или отключить, но обеспечивает защиту от потенциально опасных или нежелательных сообщений из ваших почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="641f2-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="641f2-131">Фишинговые сообщения с высокой достоверности и вредоносные программы должны быть на карантине.</span><span class="sxs-lookup"><span data-stu-id="641f2-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="641f2-132">Только администраторы могут управлять сообщениями, которые находятся на карантине как вредоносные программы или фишинговые сообщения с высокой достоверности, а также сообщать о ложных срабатываниях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="641f2-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="641f2-133">Дополнительные сведения см. в под управлением сообщений и файлов на карантине от имени [администратора в EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="641f2-134">Подробнее о том, почему мы это делаем</span><span class="sxs-lookup"><span data-stu-id="641f2-134">More on why we're doing this</span></span>

<span data-ttu-id="641f2-135">Безопасность по умолчанию обеспечивается тем же образом: мы выполнят те же действия с сообщением, что и если вы знаете, что сообщение вредоносное, даже если настроенное исключение позволит доставить сообщение в противном случае.</span><span class="sxs-lookup"><span data-stu-id="641f2-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="641f2-136">Это тот же подход, который мы всегда использовали для вредоносных программ, и теперь мы расширяем это поведение до фишинговых сообщений с высокой достоверности.</span><span class="sxs-lookup"><span data-stu-id="641f2-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="641f2-137">Наши данные указывают, что пользователь в 30 раз чаще щелкает вредоносную ссылку в сообщениях в папке нежелательной почты и карантине.</span><span class="sxs-lookup"><span data-stu-id="641f2-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="641f2-138">Наши данные также указывают, что коэффициент ложного срабатывания (хорошие сообщения помечены как плохое) для фишинговых сообщений с высокой достоверности очень низкий, и администраторы могут разрешать любые ложные срабатывания с помощью отправленных администратором сообщений.</span><span class="sxs-lookup"><span data-stu-id="641f2-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="641f2-139">Мы также определили, что списки разрешенных отправителей и разрешенных доменов в политиках борьбы с нежелательной почтой и надежных отправителей в Outlook слишком обширны и причиняют больше вреда, чем пользы.</span><span class="sxs-lookup"><span data-stu-id="641f2-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="641f2-140">Другими словами, мы действуем от вашего имени, чтобы ваши пользователи не скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="641f2-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="641f2-141">Exceptions</span><span class="sxs-lookup"><span data-stu-id="641f2-141">Exceptions</span></span>

<span data-ttu-id="641f2-142">Единственное переопределение, которое позволяет сообщению с высокой достоверности обходить фильтрацию, — это правила потока почты Exchange (также известные как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="641f2-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="641f2-143">Чтобы использовать правила потока почты для обхода фильтрации, см. "Использование правил потока почты для применения [SCL в сообщениях".](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="641f2-144">Переопределения следует использовать только в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="641f2-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="641f2-145">Имитации фишинга: имитированные атаки могут помочь определить уязвимых пользователей до того, как они понвяют вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="641f2-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="641f2-146">Почтовые ящики безопасности и secOps: выделенные почтовые ящики, используемые группами безопасности для получения неотобраченных сообщений (как хороший, так и плохой).</span><span class="sxs-lookup"><span data-stu-id="641f2-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="641f2-147">Затем Teams может просмотреть, содержат ли они вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="641f2-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="641f2-148">Сторонние фильтры: защита по умолчанию не применяется, если запись MX домена не относится к Office 365.</span><span class="sxs-lookup"><span data-stu-id="641f2-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="641f2-149">Ложные срабатываия: может потребоваться временно разрешить определенные сообщения, которые по-прежнему анализируются корпорацией Майкрософт, с помощью от [отправленных администратором сообщений.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="641f2-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="641f2-150">Как и во всех переопределениях, рекомендуется, чтобы они были временными.</span><span class="sxs-lookup"><span data-stu-id="641f2-150">As with all overrides, it is recommended that they are temporary.</span></span>
