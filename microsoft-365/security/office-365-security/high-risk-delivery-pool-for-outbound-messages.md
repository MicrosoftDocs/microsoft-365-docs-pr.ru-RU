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
description: Узнайте, как пулы доставки используются для защиты репутации серверов электронной почты в Microsoft 365 центрах обработки данных.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137731"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="eb3e8-103">Пулы доставки исходящей почты</span><span class="sxs-lookup"><span data-stu-id="eb3e8-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eb3e8-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="eb3e8-104">**Applies to**</span></span>
- [<span data-ttu-id="eb3e8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eb3e8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eb3e8-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="eb3e8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eb3e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb3e8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eb3e8-108">Серверы электронной почты в Microsoft 365 центрах обработки данных могут быть временно виновными в отправке нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="eb3e8-109">Например, вредоносная или вредоносная атака нежелательной почты в локальной организации электронной почты, которая отправляет исходящие сообщения через Microsoft 365 или Microsoft 365 учетные записи.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="eb3e8-110">Злоумышленники также пытаются избежать обнаружения, передав сообщения Microsoft 365 переадтрансляции.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="eb3e8-111">Эти сценарии могут привести к ip-адресу затронутых Microsoft 365 серверов центра обработки данных, появляющихся в сторонних блоклистах.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="eb3e8-112">Организации электронной почты назначения, которые используют эти блоклисты, отклоняет электронную почту из этих источников сообщений.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="eb3e8-113">Пул доставки с высоким риском</span><span class="sxs-lookup"><span data-stu-id="eb3e8-113">High-risk delivery pool</span></span>
<span data-ttu-id="eb3e8-114">Чтобы предотвратить это, все исходящие сообщения с Microsoft 365 серверов центра обработки данных, которые, как определено, [](configure-the-outbound-spam-policy.md) являются нежелательной почтой или превышают пределы отправки политик отправки или исходящие политики нежелательной почты, отправляются через пул доставки с высоким уровнем _риска._ [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="eb3e8-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="eb3e8-115">Пул доставки с высоким уровнем риска — это отдельный пул IP-адресов для исходящие сообщения, которые используются только для отправки сообщений низкого качества (например, нежелательной почты и [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="eb3e8-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="eb3e8-116">Использование пула доставки с высоким уровнем риска помогает предотвратить отправку нежелательной почты обычному пулу IP-адресов для исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="eb3e8-117">Нормальный пул IP-адресов для исходящие сообщения поддерживает репутацию отправки "высококачественных" сообщений, что снижает вероятность появления этих IP-адресов в списках ip-адресов.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="eb3e8-118">Вполне реальная вероятность того, что IP-адреса в пуле доставки с высоким уровнем риска будут размещены в блокстах IP-адресов, остается, но это по проекту.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="eb3e8-119">Доставка получателям не гарантируется, так как многие организации электронной почты не будут принимать сообщения из пула доставки с высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="eb3e8-120">Дополнительные сведения см. в [сообщении Control outbound spam.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="eb3e8-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eb3e8-121">Сообщения, в которых исходный домен электронной почты не имеет записи и записи MX, определенной в общедоступных DNS, всегда отправляются через пул доставки с высоким уровнем риска, независимо от их нежелательной почты или ограничения отправки.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="eb3e8-122">Сообщения отказов</span><span class="sxs-lookup"><span data-stu-id="eb3e8-122">Bounce messages</span></span>

<span data-ttu-id="eb3e8-123">Исходящие пул доставки с высоким риском управляют доставкой для всех отчетов о невывозе (также известных как NDRs, отказов сообщений, уведомлений о состоянии доставки или DSNs).</span><span class="sxs-lookup"><span data-stu-id="eb3e8-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="eb3e8-124">Возможные причины всплеска NDRs включают:</span><span class="sxs-lookup"><span data-stu-id="eb3e8-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="eb3e8-125">Кампания подмены, которая затрагивает одного из клиентов, использующих службу.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="eb3e8-126">Атака урожая каталога.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-126">A directory harvest attack.</span></span>
- <span data-ttu-id="eb3e8-127">Атака нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-127">A spam attack.</span></span>
- <span data-ttu-id="eb3e8-128">Сервер электронной почты изгоев.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-128">A rogue email server.</span></span>

<span data-ttu-id="eb3e8-129">Все эти проблемы могут привести к резкому увеличению числа NDRs, обрабатываемых службой.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="eb3e8-130">Много раз эти NDRs, как представляется, нежелательной почты для других серверов и служб электронной почты (также известный как _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="eb3e8-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="eb3e8-131">Пул ретрансляторов</span><span class="sxs-lookup"><span data-stu-id="eb3e8-131">Relay pool</span></span>

<span data-ttu-id="eb3e8-132">Сообщения, которые передаются или передаются Microsoft 365 в определенных сценариях, будут отправляться с помощью специального пула ретрансляторов, так как пункт назначения не должен рассматриваться Microsoft 365 как фактический отправитель.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="eb3e8-133">Для нас важно изолировать этот трафик электронной почты, так как существуют законные и недопустимые сценарии автоматической переадтрансляции или ретрансляции электронной почты из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="eb3e8-134">Как и в пуле доставки с высоким уровнем риска, для ретрансляции почты используется отдельный пул IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="eb3e8-135">Этот пул адресов не публикуется, так как он часто может изменяться, и он не входит в опубликованную запись SPF для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="eb3e8-136">Microsoft 365, чтобы убедиться, что исходный отправитель является законным, чтобы мы могли с уверенностью доставить переад.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="eb3e8-137">Переданное или переданное сообщение должно соответствовать одному из следующих критериев, чтобы избежать использования пула ретрансляторов:</span><span class="sxs-lookup"><span data-stu-id="eb3e8-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="eb3e8-138">Исходящие отправитель находится в [принятом домене](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="eb3e8-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="eb3e8-139">SPF передается, когда сообщение приходит к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="eb3e8-140">DKIM в домене отправитель передается, когда сообщение приходит к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="eb3e8-141">Вы можете сказать, что сообщение было отправлено через пул ретрансляторов, посмотрев IP-адрес исходящем сервере (пул ретрансляторов будет в диапазоне 40.95.0.0/16) или посмотрев имя исходящем сервере (будет иметь "rly" в имени).</span><span class="sxs-lookup"><span data-stu-id="eb3e8-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="eb3e8-142">В случаях, когда мы можем проверить подлинность отправитель, мы используем схему переописывающего отправитель (SRS), чтобы помочь системе электронной почты получателя узнать, что отправленное сообщение из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="eb3e8-143">Вы можете узнать больше о том, как это работает и что можно сделать, чтобы убедиться, что отправляющий домен проходит проверку подлинности в схеме переописания отправитель [(SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme)в Office 365 .</span><span class="sxs-lookup"><span data-stu-id="eb3e8-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="eb3e8-144">Чтобы DKIM работал, убедитесь, что вы включаете DKIM для отправки домена.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="eb3e8-145">Например, fabrikam.com является частью contoso.com и определяется в принятых доменах организации.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="eb3e8-146">Если отправитель сообщения sender@fabrikam.com, DKIM необходимо включить для fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="eb3e8-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="eb3e8-147">Вы можете прочитать о том, как включить в Use DKIM для проверки исходящие сообщения электронной почты, отправленной [из настраиваемого домена.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="eb3e8-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="eb3e8-148">Чтобы добавить настраиваемые домены, выполните действия в [Add a domain to Microsoft 365.](../../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="eb3e8-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>
