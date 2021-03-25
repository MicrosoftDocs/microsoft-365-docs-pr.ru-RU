---
title: Поддержка проверки подписанных сообщений с подписанными ключами домена почтой (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Узнайте о проверке подписанных DKIM сообщений в Exchange Online Protection и Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206458"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="13a8b-103">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="13a8b-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="13a8b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="13a8b-104">**Applies to**</span></span>
- [<span data-ttu-id="13a8b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="13a8b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="13a8b-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="13a8b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="13a8b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13a8b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="13a8b-108">Exchange Online Protection (EOP) и Exchange Online поддерживают входящие проверки сообщений с идентифицированной почтой доменных ключей[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="13a8b-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="13a8b-109">DKIM проверяет, что сообщение электронной почты не было поддельным кем-то  другим, и было отправлено из домена, в который оно поступило. </span><span class="sxs-lookup"><span data-stu-id="13a8b-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="13a8b-110">Оно связывает сообщение электронной почты с организацией, отправив ее.</span><span class="sxs-lookup"><span data-stu-id="13a8b-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="13a8b-111">Проверка DKIM автоматически используется для всех сообщений, отправленных с помощью IPv6.</span><span class="sxs-lookup"><span data-stu-id="13a8b-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="13a8b-112">Microsoft 365 также поддерживает DKIM при отправлении почты по IPv4.</span><span class="sxs-lookup"><span data-stu-id="13a8b-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="13a8b-113">(Дополнительные сведения о поддержке IPv6 см. в сообщении [Support for anonymous inbound email messages over IPv6.)](support-for-anonymous-inbound-email-messages-over-ipv6.md)</span><span class="sxs-lookup"><span data-stu-id="13a8b-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="13a8b-114">DKIM проверяет цифровое подписанное сообщение, которое DKIM-Signature в загоне заглавных окне сообщений.</span><span class="sxs-lookup"><span data-stu-id="13a8b-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="13a8b-115">Результаты проверки DKIM-Signature штампуются в Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="13a8b-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="13a8b-116">Текст заголовка сообщения имеет указанные ниже формат (где contoso.com  отправитель).</span><span class="sxs-lookup"><span data-stu-id="13a8b-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="13a8b-117">Дополнительные сведения о заглавной Authentication-Results см. в сообщении RFC 7001 (Поле загонщика сообщений для указания состояния проверки подлинности[сообщений.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="13a8b-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="13a8b-118">Реализация DKIM Корпорации Майкрософт соответствует этой RFC.</span><span class="sxs-lookup"><span data-stu-id="13a8b-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="13a8b-119">Администраторы могут создавать [правила](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) потока почты Exchange (также известные как правила транспорта) по результатам проверки DKIM.</span><span class="sxs-lookup"><span data-stu-id="13a8b-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="13a8b-120">Эти правила потока почты позволят администраторам фильтровать или маршрутить сообщения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="13a8b-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>