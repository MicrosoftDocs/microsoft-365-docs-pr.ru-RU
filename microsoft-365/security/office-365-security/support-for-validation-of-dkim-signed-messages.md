---
title: Поддержка проверки сообщений с подписью DKIM
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
description: Проверка сообщений с подписью DKIM в Exchange Online Protection и Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290265"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="b1543-103">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="b1543-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1543-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="b1543-104">**Applies to**</span></span>
- [<span data-ttu-id="b1543-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b1543-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b1543-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="b1543-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b1543-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1543-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b1543-108">Exchange Online Protection (EOP) и Exchange Online поддерживают входящие проверки сообщений почты с идентифицированными ключами домена[(DKIM).](https://www.rfc-editor.org/rfc/rfc6376.txt)</span><span class="sxs-lookup"><span data-stu-id="b1543-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="b1543-109">DKIM проверяет, не было ли  сообщение электронной почты подменой другими  и отправлено из домена, с него поступило сообщение.</span><span class="sxs-lookup"><span data-stu-id="b1543-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="b1543-110">Оно связывает сообщение электронной почты с организацией, которая его отправила.</span><span class="sxs-lookup"><span data-stu-id="b1543-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="b1543-111">Проверка DKIM используется автоматически для всех сообщений, отправленных с помощью IPv6.</span><span class="sxs-lookup"><span data-stu-id="b1543-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="b1543-112">Microsoft 365 также поддерживает DKIM при пересылке почты по IPv4.</span><span class="sxs-lookup"><span data-stu-id="b1543-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="b1543-113">(Дополнительные сведения о поддержке IPv6 см. в поддержке анонимных входящие сообщения электронной почты [по IPv6.)](support-for-anonymous-inbound-email-messages-over-ipv6.md)</span><span class="sxs-lookup"><span data-stu-id="b1543-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="b1543-114">DKIM проверяет сообщение с цифровой подписью, которое отображается в DKIM-Signature в его загоне.</span><span class="sxs-lookup"><span data-stu-id="b1543-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="b1543-115">Результаты проверки DKIM-Signature помеются в Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="b1543-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="b1543-116">Текст заголовка сообщения имеет указанные ниже формат (где contoso.com  отправитель).</span><span class="sxs-lookup"><span data-stu-id="b1543-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="b1543-117">Дополнительные сведения о Authentication-Results сообщений см. в документе RFC 7001 ( Поле загона сообщения для указания состояния проверки[подлинности сообщений.](https://www.rfc-editor.org/rfc/rfc7001.txt)</span><span class="sxs-lookup"><span data-stu-id="b1543-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="b1543-118">Реализация DKIM корпорации Майкрософт соответствует этому RFC.</span><span class="sxs-lookup"><span data-stu-id="b1543-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="b1543-119">Администраторы могут создавать правила [потока](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) почты Exchange (также известные как правила транспорта) по результатам проверки DKIM.</span><span class="sxs-lookup"><span data-stu-id="b1543-119">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="b1543-120">Эти правила потока почты позволяют администраторам фильтровать или маршрутить сообщения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b1543-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
