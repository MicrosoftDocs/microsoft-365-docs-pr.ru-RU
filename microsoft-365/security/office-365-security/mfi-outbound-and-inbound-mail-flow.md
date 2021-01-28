---
title: Анализ потока исходящие и входящие сообщения на панели мониторинга потока почты
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
description: Администраторы могут получить сведения о потоке обработки исходящие и входящие сообщения на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029826"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="ce943-103">Анализ потока обработки исходящие и входящие сообщения в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ce943-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ce943-104">Анализ **потока** обработки исходящие и [](mail-flow-insights-v2.md) входящие почты на панели мониторинга потока обработки [](view-mail-flow-reports.md#connector-report) почты в Центре безопасности и [соответствия](https://protection.office.com) требованиям & объединяет сведения из отчета соединители и бывшего отчета об **обзоре TLS** в одном месте.</span><span class="sxs-lookup"><span data-stu-id="ce943-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="ce943-105">Виджет отображает шифрование TLS, используемую для подключения при доставке сообщений в организацию и из нее.</span><span class="sxs-lookup"><span data-stu-id="ce943-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="ce943-106">Подключения, установленные с другими службами электронной почты, шифруются по TLS, если TLS предлагается обеими сторонами.</span><span class="sxs-lookup"><span data-stu-id="ce943-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="ce943-107">Виджет предлагает моментальный снимок последней недели потока почты.</span><span class="sxs-lookup"><span data-stu-id="ce943-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Мини-виджет "Поток обработки исходящие и входящие сообщения" на панели мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="ce943-109">Сведения в мини-приложениях связаны с соединитетелями и защитой сообщений TLS в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce943-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="ce943-110">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ce943-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="ce943-111">Настройка потока почты с помощью соединителетов</span><span class="sxs-lookup"><span data-stu-id="ce943-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="ce943-112">Использование протокола TLS службой Exchange Online для защиты электронной почты</span><span class="sxs-lookup"><span data-stu-id="ce943-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="ce943-113">Технические справочные сведения о шифровании в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce943-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="ce943-114">Сообщение, защищенное при транспорте (по TLS)</span><span class="sxs-lookup"><span data-stu-id="ce943-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="ce943-115">При нажатии кнопки "Просмотреть сведения" мини-приложения на элементе "Сообщение, защищенное при передаче (с помощью **TLS)** будет показана защита TLS для сообщений, которые входят в вашу организацию и покидают ее. </span><span class="sxs-lookup"><span data-stu-id="ce943-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Сообщения, защищенные при переходе (с помощью TLS), которые появляются после нажатия кнопки "Просмотреть сведения" в мини-приложениях "Исходящие и входящие сообщения электронной почты"](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="ce943-117">В настоящее время TLS 1.2 — это наиболее безопасная версия TLS, которую предлагает Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce943-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="ce943-118">Часто необходимо знать шифрование TLS, используемую для аудита соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ce943-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="ce943-119">Вероятно, у вас нет прямых отношений с большинством исходных и почтовых серверов назначения (вы не владеете ими и не корпорацией Майкрософт), поэтому у вас нет параметров для улучшения шифрования TLS, используемого этими серверами.</span><span class="sxs-lookup"><span data-stu-id="ce943-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="ce943-120">Однако вы можете [](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) использовать соединители для обеспечения наилучшей доступной защиты TLS для сообщений, которые отправляются между вашими почтовыми серверами и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce943-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="ce943-121">Поток почты между Microsoft 365 и вашими серверами электронной почты или серверами, принадлежащими вашим партнерам, часто более важен и чувствителен, чем обычные сообщения, поэтому к этим сообщениям необходимо применить дополнительную безопасность и безопасность.</span><span class="sxs-lookup"><span data-stu-id="ce943-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="ce943-122">Вы можете обновить или исправить собственные почтовые серверы, чтобы улучшить используемую шифрование TLS, или связаться с партнерами, чтобы сделать то же самое.</span><span class="sxs-lookup"><span data-stu-id="ce943-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="ce943-123">Отчет **о соединители отображает** как объем потока почты, так и шифрование TLS для сообщений, которые используют соединители Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce943-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="ce943-124">Вы можете щелкнуть ссылку **на** отчет соединители, чтобы перейти к [отчету о соединители.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="ce943-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="ce943-125">Если обнаружено связанное условие, на странице отчета соединители могут быть доступны следующие сведения: </span><span class="sxs-lookup"><span data-stu-id="ce943-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="ce943-126">**Входящий соединитель партнеров с значительным потоком почты TLS1.0**</span><span class="sxs-lookup"><span data-stu-id="ce943-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="ce943-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span><span class="sxs-lookup"><span data-stu-id="ce943-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="ce943-128">Для подключений TLS 1.0 действительно необходимо обновить или устранить проблемы с поддержкой TLS 1.0 в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce943-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce943-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ce943-129">See also</span></span>

<span data-ttu-id="ce943-130">Сведения о других сведениях на панели мониторинга потока обработки почты см. в анализе потока обработки почты в Центре безопасности [& соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ce943-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
