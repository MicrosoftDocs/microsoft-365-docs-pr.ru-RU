---
title: Безопасность по умолчанию в Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Дополнительные информацию о параметре secure by default в Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c737647202e82af0fc217c0eadb3e2573d13a9b1
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177649"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="41f7f-103">Безопасность по умолчанию в Office 365</span><span class="sxs-lookup"><span data-stu-id="41f7f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41f7f-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="41f7f-104">**Applies to**</span></span>
- [<span data-ttu-id="41f7f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41f7f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="41f7f-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="41f7f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41f7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41f7f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="41f7f-108">"Secure по умолчанию" — это термин, используемый для определения наиболее безопасных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41f7f-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="41f7f-109">Однако безопасность должна быть сбалансирована с производительностью.</span><span class="sxs-lookup"><span data-stu-id="41f7f-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="41f7f-110">Это может включать балансировку между:</span><span class="sxs-lookup"><span data-stu-id="41f7f-110">This can include balancing across:</span></span>

- <span data-ttu-id="41f7f-111">**Юность:** Параметры не должна влиять на производительность пользователей.</span><span class="sxs-lookup"><span data-stu-id="41f7f-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="41f7f-112">**Риск.** Безопасность может блокировать важные действия.</span><span class="sxs-lookup"><span data-stu-id="41f7f-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="41f7f-113">**Устаревшие параметры.** Некоторые конфигурации для старых продуктов и функций, возможно, потребуется поддерживать по бизнес-причинам, даже если новые, современные параметры улучшены.</span><span class="sxs-lookup"><span data-stu-id="41f7f-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="41f7f-114">Microsoft 365 организации с почтовыми ящиками в Exchange Online защищены Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="41f7f-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="41f7f-115">Эта защита включает в себя:</span><span class="sxs-lookup"><span data-stu-id="41f7f-115">This protection includes:</span></span>

- <span data-ttu-id="41f7f-116">Электронная почта с подозрительными вредоносными программами автоматически будет на карантине, и получатели будут уведомлены.</span><span class="sxs-lookup"><span data-stu-id="41f7f-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="41f7f-117">См. в программе Настройка политик [борьбы с вредоносными программами в EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="41f7f-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="41f7f-118">Электронная почта, идентифицированная как фишинг с высоким уровнем доверия, будет обрабатываться в соответствии с действием политики защиты от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="41f7f-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="41f7f-119">См. [в сообщении Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="41f7f-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="41f7f-120">Дополнительные сведения об EOP см. [в Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="41f7f-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="41f7f-121">Поскольку Корпорация Майкрософт хочет обеспечить безопасность наших клиентов по умолчанию, некоторые клиенты не применяются для вредоносных программ или высокой уверенности в фишинге.</span><span class="sxs-lookup"><span data-stu-id="41f7f-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="41f7f-122">Эти переопределения включают:</span><span class="sxs-lookup"><span data-stu-id="41f7f-122">These overrides include:</span></span>

- <span data-ttu-id="41f7f-123">Разрешенные списки отправитель или разрешенные списки доменов (политики по борьбе со спамом)</span><span class="sxs-lookup"><span data-stu-id="41f7f-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="41f7f-124">Outlook Сейф отправителей</span><span class="sxs-lookup"><span data-stu-id="41f7f-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="41f7f-125">СПИСОК IP-адресов (фильтрация подключений)</span><span class="sxs-lookup"><span data-stu-id="41f7f-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="41f7f-126">Дополнительные сведения об этих переопределениях можно найти в [списках создания безопасных отправитель.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="41f7f-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="41f7f-127">Мы ухудшили действие move **message to junk email folder** action for a High confidence **phishing email** verdict in EOP anti-spam policies.</span><span class="sxs-lookup"><span data-stu-id="41f7f-127">We have deprecated the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="41f7f-128">Политики защиты от нежелательной почты, которые используют это действие для высокой уверенности в фишинговых сообщениях, будут преобразованы в сообщение **карантина.**</span><span class="sxs-lookup"><span data-stu-id="41f7f-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="41f7f-129">Действие **перенаправления** на адрес электронной почты для фишинговых сообщений с высокой уверенностью не влияет.</span><span class="sxs-lookup"><span data-stu-id="41f7f-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="41f7f-130">Secure по умолчанию не является параметром, который можно отключить или отключить, но это способ фильтрации работает из окна, чтобы сохранить потенциально опасные или нежелательные сообщения из почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="41f7f-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="41f7f-131">Вредоносные программы и сообщения фишинга с высокой уверенностью должны быть на карантине.</span><span class="sxs-lookup"><span data-stu-id="41f7f-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="41f7f-132">Только администраторы могут управлять сообщениями, которые находятся на карантине в качестве вредоносных программ или высокой достоверности фишинга, и они также могут сообщать о ложных срабатываниях в Microsoft оттуда.</span><span class="sxs-lookup"><span data-stu-id="41f7f-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="41f7f-133">Дополнительные сведения см. в [статью Управление карантинными](manage-quarantined-messages-and-files.md) сообщениями и файлами в качестве администратора в EOP</span><span class="sxs-lookup"><span data-stu-id="41f7f-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="41f7f-134">Подробнее о том, почему мы это делаем</span><span class="sxs-lookup"><span data-stu-id="41f7f-134">More on why we're doing this</span></span>

<span data-ttu-id="41f7f-135">Дух безопасности по умолчанию: мы примем те же действия в сообщении, которое будет приниматься, если вы знали, что сообщение вредоносное, даже если настроенное исключение в противном случае позволит доставить сообщение.</span><span class="sxs-lookup"><span data-stu-id="41f7f-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="41f7f-136">Это тот же подход, который мы всегда использовали для вредоносных программ, и теперь мы расширяем это же поведение до сообщений высокой уверенности в фишинге.</span><span class="sxs-lookup"><span data-stu-id="41f7f-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="41f7f-137">Наши данные указывают на то, что у пользователя в 30 раз больше шансов щелкнуть вредоносную ссылку в сообщениях в папке нежелательной почты по сравнению с карантином.</span><span class="sxs-lookup"><span data-stu-id="41f7f-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="41f7f-138">Наши данные также указывают на то, что уровень ложного срабатывания (хорошие сообщения помечены как плохие) для сообщений с высоким уровнем доверия для фишинговых сообщений очень низкий, и администраторы могут устранять любые ложные срабатывания с помощью представлений администратора.</span><span class="sxs-lookup"><span data-stu-id="41f7f-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="41f7f-139">Мы также определили, что разрешенный отправитель и разрешенные списки доменов в политиках по борьбе со спамом и Сейф отправителей в Outlook слишком широки и причиняют больше вреда, чем пользы.</span><span class="sxs-lookup"><span data-stu-id="41f7f-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="41f7f-140">Другими словами: в качестве службы безопасности мы действуем от вашего имени, чтобы предотвратить скомпрометировать пользователей.</span><span class="sxs-lookup"><span data-stu-id="41f7f-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span>

## <a name="exceptions"></a><span data-ttu-id="41f7f-141">Исключения</span><span class="sxs-lookup"><span data-stu-id="41f7f-141">Exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="41f7f-142">В августе 2021 г. безопасность по умолчанию будет распространена на Exchange (также известные как правила транспорта).</span><span class="sxs-lookup"><span data-stu-id="41f7f-142">In August 2021, secure by default will be extended to Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="41f7f-143">Если вы используете правила потока почты, чтобы разрешить сторонние фишинговые симуляции или неотгрузку в почтовые ящики операции безопасности, в конечном итоге необходимо устранить эти правила и перейти к использованию продвинутой политики доставки, когда эта функция доступна для вас [](configure-advanced-delivery.md) _._</span><span class="sxs-lookup"><span data-stu-id="41f7f-143">If you use mail flow rules to allow third-party phishing simulations or unfiltered delivery to security operation mailboxes, you eventually need to eliminate these rules and switch to using the [advanced delivery policy](configure-advanced-delivery.md) _when the feature is available to you_.</span></span>

<span data-ttu-id="41f7f-144">Единственное переопределение, которое позволяет избежать фильтрации фишинговых сообщений с высокой уверенностью, это правила потока почты.</span><span class="sxs-lookup"><span data-stu-id="41f7f-144">The only override that allows high confidence phishing message to bypass filtering is mail flow rules.</span></span> <span data-ttu-id="41f7f-145">Чтобы использовать правила потока почты для обхода фильтрации, см. в рублях Использование правил потока почты для набора [SCL в сообщениях.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="41f7f-145">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="41f7f-146">Следует использовать переопределения только в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="41f7f-146">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="41f7f-147">Имитация фишинга. Смоделированные атаки помогут определить уязвимых пользователей до того, как реальная атака ударит по организации.</span><span class="sxs-lookup"><span data-stu-id="41f7f-147">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="41f7f-148">Почтовые ящики Security/SecOps: выделенные почтовые ящики, используемые группами безопасности для получения неотобраченных сообщений (как хороших, так и плохих).</span><span class="sxs-lookup"><span data-stu-id="41f7f-148">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="41f7f-149">Teams затем можно просмотреть, содержат ли они вредоносный контент.</span><span class="sxs-lookup"><span data-stu-id="41f7f-149">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="41f7f-150">Сторонние фильтры: Secure по умолчанию не применяется, если запись MX домена не указывает на Office 365.</span><span class="sxs-lookup"><span data-stu-id="41f7f-150">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="41f7f-151">Ложные срабатыва; возможно, необходимо временно разрешить определенные сообщения, которые по-прежнему анализируются Корпорацией Майкрософт с помощью [представлений администратора.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="41f7f-151">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="41f7f-152">Как и во всех переопределениях, рекомендуется, чтобы они были временными.</span><span class="sxs-lookup"><span data-stu-id="41f7f-152">As with all overrides, it is recommended that they are temporary.</span></span>
