---
title: Пул доставки сообщений с высоким уровнем опасности
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Узнайте, как пул доставки с высоким уровнем риска используется для защиты репутации почтовых серверов в центрах обработки данных Microsoft 365.
ms.openlocfilehash: 7fb4788361534335be1e07bae44ed7511bebe434
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638038"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="f4e1c-103">Пул доставки сообщений с высоким уровнем опасности</span><span class="sxs-lookup"><span data-stu-id="f4e1c-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="f4e1c-104">Почтовые серверы в центрах обработки данных Microsoft 365 могут временно гуилти от отправки нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="f4e1c-105">Например, вредоносная или вредоносная Нежелательная почта в локальной организации электронной почты, которая отправляет исходящую почту через Microsoft 365 или скомпрометированные учетные записи Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="f4e1c-106">Эти сценарии могут привести к тому, что IP-адрес уязвимых серверов центра обработки данных Microsoft 365 появлялся на сторонних блочных списках.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="f4e1c-107">Конечные организации электронной почты, которые используют эти списки блокировок, будут отклонять почту из этих источников сообщений.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="f4e1c-108">Чтобы избежать этого, все исходящие сообщения от серверов Microsoft 365 Datacenter, которые определены как нежелательная почта или которые превышают ограничения на отправку [службы](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) или [исходящей почты](configure-the-outbound-spam-policy.md) , отправляются через _пул доставки с высоким уровнем риска_.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="f4e1c-109">Пул доставки с высоким уровнем риска — это дополнительный пул IP-адресов для исходящей электронной почты, который используется только для отправки сообщений "низкому качеству" (например, спама и почтовых [рассеивания](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="f4e1c-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="f4e1c-110">Использование пула с высоким уровнем риска помогает предотвратить отправку нежелательных сообщений из пула IP-адресов для исходящей электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="f4e1c-111">Обычный пул IP-адресов для исходящей электронной почты поддерживает сообщения с высоким качеством репутации, что снижает вероятность того, что эти IP-адреса будут отображаться в списках заблокированных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="f4e1c-112">Реальная вероятность того, что IP-адреса в пуле доставки с высоким уровнем риска будут помещены в списки заблокированных IP-адресов, но это сделано по проектированию.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="f4e1c-113">Доставка предполагаемым получателям не гарантируется, так как многие организации электронной почты не принимают сообщения из пула доставки с высоким уровнем риска.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="f4e1c-114">Дополнительные сведения [см.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="f4e1c-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f4e1c-115">Сообщения, в которых исходный домен электронной почты не является записью, а запись MX, определенная в общедоступной службе DNS, всегда направляется через пул доставки с высоким уровнем риска независимо от их расстановки или ограничения.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="f4e1c-116">Сообщения Bounce</span><span class="sxs-lookup"><span data-stu-id="f4e1c-116">Bounce messages</span></span>

<span data-ttu-id="f4e1c-117">Исходящий пул доставки с высоким уровнем риска управляет доставкой для всех отчетов о недоставке (также известных как отчеты о недоставке, сообщения Bounce, уведомления о доставке или имена DSN).</span><span class="sxs-lookup"><span data-stu-id="f4e1c-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="f4e1c-118">Ниже перечислены возможные причины невозможности всплеска в отчетах о недоставке.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="f4e1c-119">Кампания с подделкой, которая влияет на одного из клиентов, использующих эту службу.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="f4e1c-120">Атака с помощью службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-120">A directory harvest attack.</span></span>

- <span data-ttu-id="f4e1c-121">Атака нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-121">A spam attack.</span></span>

- <span data-ttu-id="f4e1c-122">Незаконный сервер электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-122">A rogue email server.</span></span>

<span data-ttu-id="f4e1c-123">Все эти проблемы могут привести к резкому увеличению количества отчетов о недоставке, обрабатываемых службой.</span><span class="sxs-lookup"><span data-stu-id="f4e1c-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="f4e1c-124">Во многих случаях эти отчеты о недоставке отображаются как нежелательная почта для других серверов и служб электронной почты (также называемых почтовыми _[рассеиваниеми](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="f4e1c-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
