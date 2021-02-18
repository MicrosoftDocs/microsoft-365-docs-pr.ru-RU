---
title: Добавление поддержки анонимных входящих писем по протоколу IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать, как настроить поддержку анонимной входящие сообщения электронной почты из источников IPv6 в Exchange Online и Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290277"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="fe02b-103">Добавление поддержки анонимной входящие сообщения электронной почты по IPv6 в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe02b-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fe02b-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="fe02b-104">**Applies to**</span></span>
- [<span data-ttu-id="fe02b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fe02b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fe02b-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="fe02b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fe02b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe02b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="fe02b-108">Организации Microsoft 365 с почтовыми ящиками Exchange Online и автономные организации Exchange Online Protection (EOP) без почтовых ящиков Exchange Online поддерживают анонимную входящие сообщения электронной почты по IPv6.</span><span class="sxs-lookup"><span data-stu-id="fe02b-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="fe02b-109">Исходный почтовый сервер IPv6 должен соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="fe02b-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="fe02b-110">Исходный IPv6-адрес должен иметь допустимую запись обратного DNS-поиска (PTR), которая позволяет месту назначения найти доменное имя из IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="fe02b-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="fe02b-111">Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](http://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="fe02b-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="fe02b-112">Прежде чем ваша организация сможет получать анонимную входящие сообщения электронной почты по IPv6, администратору необходимо обратиться в службу поддержки Майкрософт и запросить ее.</span><span class="sxs-lookup"><span data-stu-id="fe02b-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="fe02b-113">Инструкции о том, как открыть запрос в службу поддержки, см. в справке для администраторов в службе поддержки для [бизнеса.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="fe02b-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="fe02b-114">После включения поддержки анонимных сообщений IPv6 в организации сообщение проходит обычную фильтрацию сообщений, предоставляемую службой.</span><span class="sxs-lookup"><span data-stu-id="fe02b-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fe02b-115">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="fe02b-115">Troubleshooting</span></span>

- <span data-ttu-id="fe02b-116">Если исходный почтовый сервер не имеет записи обратного DNS-сервера IPv6, сообщения будут отклонены со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="fe02b-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="fe02b-117">Служба 450 4.7.25 недоступна, при отправке IPv6-адреса [2a01:111:f200:2004::240] должна быть обратная запись DNS.</span><span class="sxs-lookup"><span data-stu-id="fe02b-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="fe02b-118">Если отправитель не прошел проверку SPF или DKIM, сообщения будут отклонены со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="fe02b-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="fe02b-119">450 4.7.26 Служба недоступна, сообщение, отправленное по IPv6 [2a01:111:f200:2004::240], должно пройти проверку SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="fe02b-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="fe02b-120">Если вы попытались получить анонимные сообщения IPv6 до получения отказа, сообщение будет отклонено со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="fe02b-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="fe02b-121">Служба 550 5.2.1 недоступна, [contoso.com] не принимает электронную почту по IPv6.</span><span class="sxs-lookup"><span data-stu-id="fe02b-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe02b-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fe02b-122">Related topics</span></span>

[<span data-ttu-id="fe02b-123">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="fe02b-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
