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
description: Узнайте, как пулы доставки используются для защиты репутации почтовых серверов в центрах обработки данных Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289809"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="3ef67-103">Пулы доставки исходящей почты</span><span class="sxs-lookup"><span data-stu-id="3ef67-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ef67-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="3ef67-104">**Applies to**</span></span>
- [<span data-ttu-id="3ef67-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ef67-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3ef67-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="3ef67-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="3ef67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ef67-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="3ef67-108">Почтовые серверы в центрах обработки данных Microsoft 365 могут временно отказаться от отправки нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="3ef67-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="3ef67-109">Например, это может быть вредоносная программа или вредоносная нежелаическая почта в локальной организации электронной почты, которая отправляет исходящие сообщения через Microsoft 365 или скомпрометирована учетной записью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ef67-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="3ef67-110">Злоумышленники также пытаются избежать обнаружения путем ретрансляции сообщений с помощью переадтрансляции Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ef67-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="3ef67-111">Эти сценарии могут привести к появления IP-адресов затронутых серверов центра обработки данных Microsoft 365 в сторонних списках блокирований.</span><span class="sxs-lookup"><span data-stu-id="3ef67-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="3ef67-112">Почтовые организации назначения, которые используют эти списки блокирований, будут отклонить электронную почту из этих источников сообщений.</span><span class="sxs-lookup"><span data-stu-id="3ef67-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="3ef67-113">Пул доставки с высоким уровнем риска</span><span class="sxs-lookup"><span data-stu-id="3ef67-113">High-risk delivery pool</span></span>
<span data-ttu-id="3ef67-114">Во _избежание_ этого все исходящие сообщения с серверов центра обработки данных Microsoft 365, которые определены [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) как [](configure-the-outbound-spam-policy.md) нежелательные или превышают ограничения на отправку службы или политики исходящие нежелательные сообщения, отправляются через пул доставки сообщений с высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="3ef67-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="3ef67-115">Пул доставки сообщений с высоким уровнем риска — это отдельный пул IP-адресов для исходящие сообщения электронной почты, который используется только для отправки сообщений низкого качества (например, спама и подкадровой [части).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="3ef67-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="3ef67-116">Использование пула доставки с высоким уровнем риска помогает предотвратить отправку нежелательной почты обычным пулом IP-адресов для исходящие сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3ef67-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="3ef67-117">Обычный пул IP-адресов для исходящие сообщения электронной почты сохраняет репутацию отправки сообщений высокого качества, что снижает вероятность появления этих IP-адресов в списках заблокированных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="3ef67-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="3ef67-118">Вполне реальная вероятность того, что IP-адреса в пуле доставки с высоким уровнем риска будут размещаться в списках заблокированных IP-адресов, остается, но это не так.</span><span class="sxs-lookup"><span data-stu-id="3ef67-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="3ef67-119">Доставка получателям не гарантируется, так как многие почтовые организации не будут принимать сообщения из пула доставки с высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="3ef67-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="3ef67-120">Дополнительные сведения см. в под [управлением исходящие нежелательные сообщения.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="3ef67-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3ef67-121">Сообщения, в которых исходный домен электронной почты не имеет записи A и записи MX, определенной в общедоступных службах DNS, всегда перенаправляются через пул доставки сообщений с высоким уровнем риска независимо от их спама или ограничения на отправку.</span><span class="sxs-lookup"><span data-stu-id="3ef67-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="3ef67-122">Сообщения о возврате</span><span class="sxs-lookup"><span data-stu-id="3ef67-122">Bounce messages</span></span>

<span data-ttu-id="3ef67-123">Пул доставки исходящие сообщения с высоким уровнем риска управляет доставкой всех отчетов о доставке (также известных как отчеты о доставке, сообщения о возврате, уведомления о доставке или уведомления о доставке).</span><span class="sxs-lookup"><span data-stu-id="3ef67-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="3ef67-124">Возможные причины скачка в NDRs:</span><span class="sxs-lookup"><span data-stu-id="3ef67-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="3ef67-125">Спуфинговая кампания, влияемая на одного из клиентов, использующих эту службу.</span><span class="sxs-lookup"><span data-stu-id="3ef67-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="3ef67-126">Атака с сбором каталогов.</span><span class="sxs-lookup"><span data-stu-id="3ef67-126">A directory harvest attack.</span></span>
- <span data-ttu-id="3ef67-127">Атака с нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="3ef67-127">A spam attack.</span></span>
- <span data-ttu-id="3ef67-128">Мошеннический почтовый сервер.</span><span class="sxs-lookup"><span data-stu-id="3ef67-128">A rogue email server.</span></span>

<span data-ttu-id="3ef67-129">Все эти проблемы могут привести к резкому увеличению количества обрабатываемых службой NDRS.</span><span class="sxs-lookup"><span data-stu-id="3ef67-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="3ef67-130">Много раз эти сообщения о недо доступе кажутся спамом для других почтовых серверов и служб (также известных как подкадровые _[сообщения).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="3ef67-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="3ef67-131">Пул ретрансляции</span><span class="sxs-lookup"><span data-stu-id="3ef67-131">Relay pool</span></span>

<span data-ttu-id="3ef67-132">Сообщения, перенаправленные или ретрансляторы из Microsoft 365, отправляются с помощью пула специальной ретрансляции, так как конечный пункт назначения не должен считать Microsoft 365 фактическим отправищиком.</span><span class="sxs-lookup"><span data-stu-id="3ef67-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="3ef67-133">Кроме того, важно изолировать этот трафик, так как существуют подлинные и недопустимые сценарии автозаполнения или ретрансляции электронной почты из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ef67-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="3ef67-134">Как и в пуле доставки с высоким уровнем риска, для ретрансляции почты используется отдельный пул IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="3ef67-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="3ef67-135">Этот пул адресов не публикуется, так как он может часто изменяться.</span><span class="sxs-lookup"><span data-stu-id="3ef67-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="3ef67-136">Microsoft 365 необходимо убедиться в том, что исходный отправитель является подлинным, чтобы мы могли с уверенностью доставить перенаправляемые сообщения.</span><span class="sxs-lookup"><span data-stu-id="3ef67-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="3ef67-137">Для этого необходимо пройти проверку подлинности электронной почты (SPF, DKIM и DMARC), когда сообщение приходит нам.</span><span class="sxs-lookup"><span data-stu-id="3ef67-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="3ef67-138">В случаях, когда мы можем проверить подлинность отправитель, мы используем переоценку отправитель, чтобы помочь приемнику узнать, что переадрит сообщение из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="3ef67-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="3ef67-139">Вы можете узнать больше о том, как это работает и что можно сделать, чтобы убедиться, что отправляющий домен проходит проверку подлинности в схеме переописи [отправитель (SRS).](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)</span><span class="sxs-lookup"><span data-stu-id="3ef67-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
