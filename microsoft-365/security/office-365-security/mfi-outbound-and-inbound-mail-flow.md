---
title: Почтовые ящики исходящей почты и входящей почты в панели мониторинга потока обработки почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Администраторы могут узнать об исходящих и входящих почтовых сообщениях в панели мониторинга потока обработки почты в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 347e53c51c347f12795008d39458773a94ff433f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577389"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="45514-103">Почтовые ящики исходящей почты и входящей почты в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="45514-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="45514-104">**Исходящий и входящий трафик потока обработки почты** в [информационной панели почтового потока](mail-flow-insights-v2.md) в центре безопасности & соответствия требованиям объединяет сведения из отчета о [соединителях](view-mail-flow-reports.md#connector-report) и бывший **обзорный отчет TLS** в одном месте.</span><span class="sxs-lookup"><span data-stu-id="45514-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="45514-105">Мини-приложение отображает шифрование TLS, которое используется для подключения, когда сообщения доставляются в организацию и из нее.</span><span class="sxs-lookup"><span data-stu-id="45514-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="45514-106">Протокол TLS шифрует подключения, установленные с другими почтовыми службами, если протокол TLS предоставляется обеими сторонами.</span><span class="sxs-lookup"><span data-stu-id="45514-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="45514-107">Мини-приложение предоставляет снимок последней недели движения почты.</span><span class="sxs-lookup"><span data-stu-id="45514-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Мини-приложение потока обработки входящей и исходящей почты на панели мониторинга "почтовые потоки" в центре безопасности & соответствия требованиям](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="45514-109">Сведения, приведенные в мини-приложении, относятся к соединителям и защите сообщений TLS в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45514-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="45514-110">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="45514-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="45514-111">Настройка почтового процесса с помощью соединителей</span><span class="sxs-lookup"><span data-stu-id="45514-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="45514-112">Использование протокола TLS для защиты подключений электронной почты в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="45514-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="45514-113">Технические справочные сведения о шифровании в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45514-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="45514-114">Защищенное сообщение при передаче (по протоколу TLS)</span><span class="sxs-lookup"><span data-stu-id="45514-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="45514-115">При нажатии кнопки **Просмотреть сведения** на мини-приложении всплывающее меню **сообщение защищено в транзитном (по протоколу TLS)** показывает, что требуется защита от TLS для сообщений, поступающих в организацию и выходя из нее.</span><span class="sxs-lookup"><span data-stu-id="45514-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Всплывающее меню сообщения, защищенное в транзитном транспорте (по протоколу TLS), которое появляется после нажатия кнопки Просмотр сведений в мини-приложении "почта и входящая почта](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="45514-117">В настоящее время протокол TLS 1,2 является наиболее безопасной версией протокола TLS, предоставляемой корпорацией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45514-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="45514-118">Часто необходимо знать шифрование TLS, используемое для аудита соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="45514-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="45514-119">Вероятно, у вас нет прямого отношения с большинством исходных и конечных серверов электронной почты (они не являются владельцами и не работают в корпорации Майкрософт), поэтому у вас нет большого количества вариантов для повышения уровня шифрования TLS, используемого этими серверами.</span><span class="sxs-lookup"><span data-stu-id="45514-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="45514-120">Однако вы можете использовать [соединители](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) , чтобы обеспечить наилучшую доступную защиту TLS для сообщений, отправляемых между серверами электронной почты и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45514-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="45514-121">Обмен сообщениями между Microsoft 365 и своими почтовыми серверами или серверами, принадлежащими вашим партнерам, часто является более важным и конфиденциальным, чем обычные сообщения, поэтому необходимо применить к ним дополнительную защиту и вигиланце.</span><span class="sxs-lookup"><span data-stu-id="45514-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="45514-122">Вы можете обновить или исправить свои почтовые серверы, чтобы повысить уровень используемого шифрования TLS, или обратиться к своим партнерам для выполнения этих действий.</span><span class="sxs-lookup"><span data-stu-id="45514-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="45514-123">В **отчете о соединителе** отображается как громкость потока обработки почты, так и шифрование TLS для сообщений, использующих соединители Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45514-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="45514-124">Вы можете щелкнуть ссылку на **отчет соединителя** , чтобы перейти к [отчету по соединителю](view-mail-flow-reports.md#connector-report).</span><span class="sxs-lookup"><span data-stu-id="45514-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="45514-125">Если было обнаружено связанное условие, на странице " **соединительный отчет** " могут быть доступны следующие аналитики:</span><span class="sxs-lookup"><span data-stu-id="45514-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="45514-126">**Входящий соединитель партнера Просмотр большого потока обработки почты TLS 1.0**</span><span class="sxs-lookup"><span data-stu-id="45514-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="45514-127">**Входящий локальный Соединитель Просмотр большого потока обработки почты TLS 1.0**</span><span class="sxs-lookup"><span data-stu-id="45514-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="45514-128">Для подключений по протоколу TLS 1,0 необходимо обновить или обновить сервер электронной почты или сервер вашего партнера, чтобы избежать проблем, когда поддержка протокола TLS 1,0 в конечном счете является устаревшей в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45514-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="45514-129">См. также</span><span class="sxs-lookup"><span data-stu-id="45514-129">See also</span></span>

<span data-ttu-id="45514-130">Сведения о других аналитиках в панели мониторинга для почтового процесса приведены в статье сведения о [почтовых сообщениях в центре безопасности & соответствия требованиям](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="45514-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
