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
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599915"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="a462c-103">Пулы доставки исходящей почты</span><span class="sxs-lookup"><span data-stu-id="a462c-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a462c-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="a462c-104">**Applies to**</span></span>
- [<span data-ttu-id="a462c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a462c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a462c-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="a462c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a462c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a462c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a462c-108">Серверы электронной почты в центрах обработки данных Microsoft 365 могут быть временно виновными в отправке нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a462c-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="a462c-109">Например, вредоносная или вредоносная спам-атака в локальной организации электронной почты, которая отправляет исходящие сообщения через Microsoft 365 или скомпрометирована учетной записью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a462c-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="a462c-110">Злоумышленники также пытаются избежать обнаружения, передав сообщения через переадтранслятор Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a462c-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="a462c-111">Эти сценарии могут привести к ip-адресу затронутых серверов центра обработки данных Microsoft 365, которые отображаются в сторонних блок-листах.</span><span class="sxs-lookup"><span data-stu-id="a462c-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="a462c-112">Организации электронной почты назначения, которые используют эти блоклисты, отклоняет электронную почту из этих источников сообщений.</span><span class="sxs-lookup"><span data-stu-id="a462c-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="a462c-113">Пул доставки с высоким риском</span><span class="sxs-lookup"><span data-stu-id="a462c-113">High-risk delivery pool</span></span>
<span data-ttu-id="a462c-114">Чтобы предотвратить это, все исходящие сообщения с серверов центра обработки данных Microsoft 365, которые, [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) как [](configure-the-outbound-spam-policy.md) определено, являются нежелательной почтой или превышают пределы отправки политик отправки или исходящие политики нежелательной почты, отправляются через пул доставки с высоким уровнем _риска._</span><span class="sxs-lookup"><span data-stu-id="a462c-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="a462c-115">Пул доставки с высоким уровнем риска — это отдельный пул IP-адресов для исходящие сообщения, которые используются только для отправки сообщений низкого качества (например, нежелательной почты и [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a462c-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="a462c-116">Использование пула доставки с высоким уровнем риска помогает предотвратить отправку нежелательной почты обычному пулу IP-адресов для исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="a462c-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="a462c-117">Нормальный пул IP-адресов для исходящие сообщения поддерживает репутацию отправки "высококачественных" сообщений, что снижает вероятность появления этих IP-адресов в списках ip-адресов.</span><span class="sxs-lookup"><span data-stu-id="a462c-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="a462c-118">Вполне реальная вероятность того, что IP-адреса в пуле доставки с высоким уровнем риска будут размещены в блокстах IP-адресов, остается, но это по проекту.</span><span class="sxs-lookup"><span data-stu-id="a462c-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="a462c-119">Доставка получателям не гарантируется, так как многие организации электронной почты не будут принимать сообщения из пула доставки с высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="a462c-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="a462c-120">Дополнительные сведения см. в [сообщении Control outbound spam.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="a462c-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a462c-121">Сообщения, в которых исходный домен электронной почты не имеет записи и записи MX, определенной в общедоступных DNS, всегда отправляются через пул доставки с высоким уровнем риска, независимо от их нежелательной почты или ограничения отправки.</span><span class="sxs-lookup"><span data-stu-id="a462c-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="a462c-122">Сообщения отказов</span><span class="sxs-lookup"><span data-stu-id="a462c-122">Bounce messages</span></span>

<span data-ttu-id="a462c-123">Исходящие пул доставки с высоким риском управляют доставкой для всех отчетов о невывозе (также известных как NDRs, отказов сообщений, уведомлений о состоянии доставки или DSNs).</span><span class="sxs-lookup"><span data-stu-id="a462c-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="a462c-124">Возможные причины всплеска NDRs включают:</span><span class="sxs-lookup"><span data-stu-id="a462c-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="a462c-125">Кампания подмены, которая затрагивает одного из клиентов, использующих службу.</span><span class="sxs-lookup"><span data-stu-id="a462c-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="a462c-126">Атака урожая каталога.</span><span class="sxs-lookup"><span data-stu-id="a462c-126">A directory harvest attack.</span></span>
- <span data-ttu-id="a462c-127">Атака нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a462c-127">A spam attack.</span></span>
- <span data-ttu-id="a462c-128">Сервер электронной почты изгоев.</span><span class="sxs-lookup"><span data-stu-id="a462c-128">A rogue email server.</span></span>

<span data-ttu-id="a462c-129">Все эти проблемы могут привести к резкому увеличению числа NDRs, обрабатываемых службой.</span><span class="sxs-lookup"><span data-stu-id="a462c-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="a462c-130">Много раз эти NDRs, как представляется, нежелательной почты для других серверов и служб электронной почты (также известный как _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="a462c-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
