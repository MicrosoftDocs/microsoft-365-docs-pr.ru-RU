---
title: Пулы доставки исходящей почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Узнайте, как пулы доставки используются для защиты репутации серверов электронной почты в центрах обработки данных Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 461b5f9aa0407c5115ab84a075c793139a8b4305
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205398"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="80137-103">Пулы доставки исходящей почты</span><span class="sxs-lookup"><span data-stu-id="80137-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80137-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="80137-104">**Applies to**</span></span>
- [<span data-ttu-id="80137-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="80137-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="80137-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="80137-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="80137-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80137-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="80137-108">Серверы электронной почты в центрах обработки данных Microsoft 365 могут быть временно виновными в отправке нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="80137-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="80137-109">Например, вредоносная или вредоносная спам-атака в локальной организации электронной почты, которая отправляет исходящие сообщения через Microsoft 365 или скомпрометирована учетной записью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80137-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="80137-110">Злоумышленники также пытаются избежать обнаружения, передав сообщения через переадтранслятор Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80137-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="80137-111">Эти сценарии могут привести к ip-адресу затронутых серверов центра обработки данных Microsoft 365, которые отображаются в сторонних списках блоков.</span><span class="sxs-lookup"><span data-stu-id="80137-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="80137-112">Организации электронной почты назначения, которые используют эти списки блоков, будут отклонить электронную почту из этих источников сообщений.</span><span class="sxs-lookup"><span data-stu-id="80137-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="80137-113">Пул доставки с высоким риском</span><span class="sxs-lookup"><span data-stu-id="80137-113">High-risk delivery pool</span></span>
<span data-ttu-id="80137-114">Чтобы предотвратить это, все исходящие сообщения с серверов центра обработки данных Microsoft 365, которые, [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) как [](configure-the-outbound-spam-policy.md) определено, являются нежелательной почтой или превышают пределы отправки политик отправки или исходящие политики нежелательной почты, отправляются через пул доставки с высоким уровнем _риска._</span><span class="sxs-lookup"><span data-stu-id="80137-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="80137-115">Пул доставки с высоким уровнем риска — это отдельный пул IP-адресов для исходящие сообщения, которые используются только для отправки сообщений низкого качества (например, нежелательной почты и [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="80137-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="80137-116">Использование пула доставки с высоким уровнем риска помогает предотвратить отправку нежелательной почты обычному пулу IP-адресов для исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="80137-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="80137-117">Нормальный пул IP-адресов для исходящие сообщения поддерживает репутацию отправки "высококачественных" сообщений, что снижает вероятность появления этих IP-адресов в списках блоков IP.</span><span class="sxs-lookup"><span data-stu-id="80137-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="80137-118">Реальная вероятность того, что IP-адреса в пуле доставки с высоким уровнем риска будут размещены в списках блоков IP, остается, но это по проекту.</span><span class="sxs-lookup"><span data-stu-id="80137-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="80137-119">Доставка получателям не гарантируется, так как многие организации электронной почты не будут принимать сообщения из пула доставки с высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="80137-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="80137-120">Дополнительные сведения см. в [сообщении Control outbound spam.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="80137-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="80137-121">Сообщения, в которых исходный домен электронной почты не имеет записи и записи MX, определенной в общедоступных DNS, всегда отправляются через пул доставки с высоким уровнем риска, независимо от их нежелательной почты или ограничения отправки.</span><span class="sxs-lookup"><span data-stu-id="80137-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="80137-122">Сообщения отказов</span><span class="sxs-lookup"><span data-stu-id="80137-122">Bounce messages</span></span>

<span data-ttu-id="80137-123">Исходящие пул доставки с высоким риском управляют доставкой для всех отчетов о невывозе (также известных как NDRs, отказов сообщений, уведомлений о состоянии доставки или DSNs).</span><span class="sxs-lookup"><span data-stu-id="80137-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="80137-124">Возможные причины всплеска NDRs включают:</span><span class="sxs-lookup"><span data-stu-id="80137-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="80137-125">Кампания подмены, которая затрагивает одного из клиентов, использующих службу.</span><span class="sxs-lookup"><span data-stu-id="80137-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="80137-126">Атака урожая каталога.</span><span class="sxs-lookup"><span data-stu-id="80137-126">A directory harvest attack.</span></span>
- <span data-ttu-id="80137-127">Атака нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="80137-127">A spam attack.</span></span>
- <span data-ttu-id="80137-128">Сервер электронной почты изгоев.</span><span class="sxs-lookup"><span data-stu-id="80137-128">A rogue email server.</span></span>

<span data-ttu-id="80137-129">Все эти проблемы могут привести к резкому увеличению числа NDRs, обрабатываемых службой.</span><span class="sxs-lookup"><span data-stu-id="80137-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="80137-130">Много раз эти NDRs, как представляется, нежелательной почты для других серверов и служб электронной почты (также известный как _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="80137-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="80137-131">Пул ретрансляторов</span><span class="sxs-lookup"><span data-stu-id="80137-131">Relay pool</span></span>

<span data-ttu-id="80137-132">Сообщения, которые передаются или передаются из Microsoft 365, отправляются с помощью специального пула ретрансляторов, так как конечный пункт назначения не должен рассматривать Microsoft 365 в качестве фактического отправитель.</span><span class="sxs-lookup"><span data-stu-id="80137-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="80137-133">Кроме того, для нас важно изолировать этот трафик, так как существуют законные и недопустимые сценарии автопровождения или ретрансляции электронной почты из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80137-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="80137-134">Как и в пуле доставки с высоким уровнем риска, для ретрансляции почты используется отдельный пул IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="80137-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="80137-135">Этот пул адресов не публикуется, так как он может часто изменяться.</span><span class="sxs-lookup"><span data-stu-id="80137-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="80137-136">Microsoft 365 должна убедиться, что исходный отправитель является законным, чтобы мы могли с уверенностью доставить перенаправли сообщение.</span><span class="sxs-lookup"><span data-stu-id="80137-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="80137-137">Для этого необходимо пройти проверку подлинности электронной почты (SPF, DKIM и DMARC).</span><span class="sxs-lookup"><span data-stu-id="80137-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="80137-138">В случаях, когда мы можем проверить подлинность отправитель, мы используем переописывание отправитель, чтобы помочь приемнику узнать, что переадверяемая сообщение из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="80137-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="80137-139">Вы можете узнать больше о том, как это работает и что можно сделать, чтобы убедиться, что отправляющий домен проходит проверку подлинности в схеме переописания отправитель [(SRS).](/office365/troubleshoot/antispam/sender-rewriting-scheme)</span><span class="sxs-lookup"><span data-stu-id="80137-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>