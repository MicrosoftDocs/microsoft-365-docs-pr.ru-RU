---
title: Представление потока исходящие и входящие сообщения в панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Администраторы могут узнать о понимании потока исходящие и входящие сообщения в панели мониторинга потока почты в Центре & соответствия требованиям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205298"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="83518-103">Представление о потоке исходящие и входящие сообщения в Центре & безопасности</span><span class="sxs-lookup"><span data-stu-id="83518-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83518-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="83518-104">**Applies to**</span></span>
- [<span data-ttu-id="83518-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="83518-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="83518-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="83518-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="83518-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83518-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="83518-108">Анализ **потока** исходящие и входящие [](mail-flow-insights-v2.md) сообщения в [](https://protection.office.com) панели мониторинга потока почты в Центре соответствия требованиям & безопасности объединяет сведения из отчета [Connector](view-mail-flow-reports.md#connector-report) и бывшего отчета об обзоре **TLS** в одном месте.</span><span class="sxs-lookup"><span data-stu-id="83518-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="83518-109">Виджет отображает шифрование TLS, которое используется для подключения при доставке сообщений в организацию и из нее.</span><span class="sxs-lookup"><span data-stu-id="83518-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="83518-110">Подключения, установленные с другими службами электронной почты, шифруются TLS, когда TLS предлагается обеими сторонами.</span><span class="sxs-lookup"><span data-stu-id="83518-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="83518-111">Виджет предлагает снимок последней недели потока почты.</span><span class="sxs-lookup"><span data-stu-id="83518-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Виджет потока исходящие и входящие сообщения в панели мониторинга потока почты в Центре & соответствия требованиям](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="83518-113">Сведения в виджете связаны с соединиттелями и защитой сообщений TLS в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83518-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="83518-114">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="83518-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="83518-115">Настройка потока почты с помощью соединители</span><span class="sxs-lookup"><span data-stu-id="83518-115">Configure mail flow using connectors</span></span>](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="83518-116">Использование протокола TLS службой Exchange Online для защиты электронной почты</span><span class="sxs-lookup"><span data-stu-id="83518-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="83518-117">Технические справочные сведения о шифровании в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83518-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="83518-118">Сообщение, защищенное при транзите (по TLS)</span><span class="sxs-lookup"><span data-stu-id="83518-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="83518-119">При нажатии кнопки **Просмотр** сведений на виджете в сообщении, защищенном при транзите **(tLS),** показана защита TLS для сообщений, въехающих и покидающих организацию.</span><span class="sxs-lookup"><span data-stu-id="83518-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Сообщения, защищенные при транзитной (tLS) вылете, который появляется после нажатия просмотра сведений о исходящие и входящие виджет электронной почты](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="83518-121">В настоящее время TLS 1.2 является самой безопасной версией TLS, которую предлагает Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83518-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="83518-122">Часто необходимо знать шифрование TLS, которое используется для аудита соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="83518-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="83518-123">Вы, вероятно, не имеете прямых связей с большинством серверов электронной почты источника и назначения (они у вас не принадлежат, и microsoft не принадлежат), поэтому у вас нет много вариантов для улучшения шифрования TLS, которое используется на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="83518-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="83518-124">Но соединители [](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) можно использовать для обеспечения наилучшей доступной защиты TLS для сообщений, отправленных между серверами электронной почты и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83518-124">But, you can use [connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="83518-125">Поток почты между Microsoft 365 и вашими собственными серверами электронной почты или серверами, принадлежащими вашим партнерам, часто более важен и чувствителен, чем обычные сообщения, поэтому к этим сообщениям необходимо применять дополнительную безопасность и бдительность.</span><span class="sxs-lookup"><span data-stu-id="83518-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="83518-126">Вы можете обновить или исправить собственные серверы электронной почты для улучшения шифрования TLS, которое используется, или связаться с партнерами, чтобы сделать то же самое.</span><span class="sxs-lookup"><span data-stu-id="83518-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="83518-127">Отчет **Соединительщика** отображает как объем потока почты, так и шифрование TLS для сообщений, которые используют соединители Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83518-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="83518-128">Чтобы перейти к отчету **Connector,** вы можете нажать ссылку на [отчет Connector.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="83518-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="83518-129">Следующие сведения могут быть доступны на странице **отчета Connector,** если обнаружено связанное условие:</span><span class="sxs-lookup"><span data-stu-id="83518-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="83518-130">**Соединитель входящий партнер видит значительный поток почты TLS1.0**</span><span class="sxs-lookup"><span data-stu-id="83518-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="83518-131">**Входящий соединитель OnPremises видит значительный поток почты TLS1.0**</span><span class="sxs-lookup"><span data-stu-id="83518-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="83518-132">Для подключений TLS 1.0 необходимо обновить или исправить сервер электронной почты или сервер вашего партнера, чтобы избежать проблем, когда поддержка TLS 1.0 в Microsoft 365 в конечном итоге будет обесценяться.</span><span class="sxs-lookup"><span data-stu-id="83518-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="83518-133">См. также</span><span class="sxs-lookup"><span data-stu-id="83518-133">See also</span></span>

<span data-ttu-id="83518-134">Сведения о других сведениях в панели мониторинга потока почты см. в странице Анализ потока почты в Центре [& соответствия](mail-flow-insights-v2.md)требованиям.</span><span class="sxs-lookup"><span data-stu-id="83518-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>