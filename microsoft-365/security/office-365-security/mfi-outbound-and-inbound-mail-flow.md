---
title: Аналитика потока обработки исходящей и входящей почты на панели мониторинга потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Администраторы могут получить аналитические сведения о потоке обработки исходящей и входящей почты на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям.
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826897"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="f71cc-103">Аналитика потока обработки исходящей и входящей почты в Центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f71cc-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="f71cc-104">Аналитика **потока обработки исходящей** почты и входящей почты на [панели мониторинга потока](mail-flow-insights-v2.md) обработки почты в Центре соответствия требованиям безопасности & объединяет информацию [отчета соединителя](view-mail-flow-reports.md#connector-report) **и обзорный отчет ранее TLS** в одном месте.</span><span class="sxs-lookup"><span data-stu-id="f71cc-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="f71cc-105">Виджет отображает шифрование TLS, используемое для подключения при доставке сообщений в организацию и из нее.</span><span class="sxs-lookup"><span data-stu-id="f71cc-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="f71cc-106">Подключения, установленные с другими почтовыми службами, шифруются с помощью протокола TLS, если TLS предлагается собейшками.</span><span class="sxs-lookup"><span data-stu-id="f71cc-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="f71cc-107">Мини-приложение предлагает моментальный снимок за последнюю неделю потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="f71cc-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Мини-приложение "Поток обработки исходящей почты" и "Поток обработки почты" на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="f71cc-109">Сведения в мини-приложении связаны с соединителями и защитой сообщений TLS в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f71cc-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="f71cc-110">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="f71cc-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="f71cc-111">Настройка потока обработки почты с помощью соединителей</span><span class="sxs-lookup"><span data-stu-id="f71cc-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="f71cc-112">Использование протокола TLS службой Exchange Online для защиты электронной почты</span><span class="sxs-lookup"><span data-stu-id="f71cc-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="f71cc-113">Технические сведения о шифровании в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f71cc-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="f71cc-114">Защищенные в пути сообщения (с помощью протокола TLS)</span><span class="sxs-lookup"><span data-stu-id="f71cc-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="f71cc-115">Если нажать **кнопку "Просмотр сведений"** в мини-приложении, всплывающие **элементы, защищенные во время передачи (с помощью протокола TLS),** показывает защиту TLS для сообщений, поступиваемых в организацию и покидая ее.</span><span class="sxs-lookup"><span data-stu-id="f71cc-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Сообщения, защищенные в пути (с помощью протокола TLS), который появляется после нажатия кнопки "Просмотр сведений" в мини-приложении "Исходящий и входящий"](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="f71cc-117">В настоящее время Microsoft 365 является самой безопасной версией TLS, предлагаемой Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f71cc-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="f71cc-118">Часто вам необходимо знать, какое шифрование TLS используется для аудита соответствия.</span><span class="sxs-lookup"><span data-stu-id="f71cc-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="f71cc-119">Скорее всего, у вас нет прямого отношения с исходным и целевым почтовыми серверами (вы не являетесь их владельцем и ни когда корпорация Майкрософт не является корпорацией Майкрософт), поэтому у вас не будет множества возможностей усовершенствования шифрования TLS, используемого этими серверами.</span><span class="sxs-lookup"><span data-stu-id="f71cc-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="f71cc-120">Однако вы можете использовать [соединители, чтобы](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) обеспечить оптимальная защита с использованием протокола TLS для сообщений, отправляемых между вашими почтовыми серверами и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f71cc-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="f71cc-121">Поток обработки почты между Microsoft 365 и собственными почтовыми серверами или серверами, принадлежащими партнерам, обычно более важны и чувствительны к информативным, поэтому вы желаете применять для этих сообщений дополнительную защиту и поднимать соблюдение этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="f71cc-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="f71cc-122">Вы можете обновить или исправить собственные почтовые серверы, чтобы улучшить используемое шифрование TLS, или посетить своим партнерам специально эту же настройку.</span><span class="sxs-lookup"><span data-stu-id="f71cc-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="f71cc-123">Отчет **о соединителях** отображает как объем потока обработки почты, так и шифрование TLS для сообщений, использующих соединители Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f71cc-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="f71cc-124">Вы можете щелкнуть **ссылку отчета** о соединителе, чтобы перейти к [отчету о соединителе.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="f71cc-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="f71cc-125">Если обнаружено связанное условие, на странице отчета **соединителя** могут отображаться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f71cc-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="f71cc-126">**Входящий партнерский соединитель, видящий значительный поток обработки TLS1.0**</span><span class="sxs-lookup"><span data-stu-id="f71cc-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="f71cc-127">**Входящий входящий соединитель, видящий значительный поток обработки почты TLS1.0**</span><span class="sxs-lookup"><span data-stu-id="f71cc-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="f71cc-128">Для подключений по протоколу TLS 1.0 действительно требуется обновить ваш почтовый сервер или сервер партнера, чтобы избежать проблем при прекращении поддержки TLS 1.0 в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f71cc-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="f71cc-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f71cc-129">See also</span></span>

<span data-ttu-id="f71cc-130">Сведения о других аналитических данных на панели мониторинга потока обработки почты см. в статье "Аналитика потока [обработки почты" в Центре безопасности & соответствия требованиям.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="f71cc-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
