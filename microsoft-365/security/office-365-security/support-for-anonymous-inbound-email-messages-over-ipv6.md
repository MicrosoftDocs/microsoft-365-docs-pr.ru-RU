---
title: Добавление поддержки анонимных входящих писем по протоколу IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администратор ы может узнать, как настроить поддержку входящей электронной почты из источников IPv6 в Exchange Online и Exchange Online Protection.
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826781"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="ac56a-103">Добавление поддержки анонимных входящих сообщений электронной почты по протоколу IPv6 в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac56a-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="ac56a-104">Организации Microsoft 365 с почтовыми ящиками Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) без почтовых ящиков Exchange Online поддерживают анонимную входящую почту по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="ac56a-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="ac56a-105">Исходный почтовый сервер IPv6 должен соответствовать обоим требованиям следующих требований:</span><span class="sxs-lookup"><span data-stu-id="ac56a-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="ac56a-106">У IPv6-адреса источника должна быть допустимая запись обратного поиска DNS (PTR), позволяющая нашему узлу найти доменное имя по IPv6-адресу.</span><span class="sxs-lookup"><span data-stu-id="ac56a-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="ac56a-107">Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](https://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="ac56a-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="ac56a-108">Прежде чем ваша организация сможет получать анонимную входящую почту по протоколу IPv6, администратору необходимо обратиться в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ac56a-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="ac56a-109">Инструкции по созданию запроса в службу поддержки см. в справке для [администраторов.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="ac56a-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="ac56a-110">После включения в организации поддержки анонимного входящего сообщения IPv6 сообщение пройдет фильтрацию обычных сообщений, предоставляемую службой.</span><span class="sxs-lookup"><span data-stu-id="ac56a-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ac56a-111">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ac56a-111">Troubleshooting</span></span>

- <span data-ttu-id="ac56a-112">Если на исходном почтовом сервере нет обратной записи обратного поиска DNS для IPv6, сообщения будут отклоняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac56a-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="ac56a-113">450 4.7.25 Служба недоступна, отправка IPv6-адреса [2a01:111:f200:2004::240] должна иметь обратную запись DNS.</span><span class="sxs-lookup"><span data-stu-id="ac56a-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="ac56a-114">Если отправитель не проходит проверку инфраструктуры политики отправителей или DKIM, сообщения будут отклоняться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac56a-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="ac56a-115">450 4.7.26 Служба недоступна, сообщение, отправленное через Протокол IPv6 [2a01:111:f200:2004::240], должно пройти проверку ИНФРАСТРУКТУРы политики отправителей или DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac56a-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="ac56a-116">При попытке получения анонимных сообщений IPv6 сообщение будет отклонено следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac56a-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="ac56a-117">550 5.2.1 Служба недоступна, [contoso.com] не принимает электронную почту через IPv6.</span><span class="sxs-lookup"><span data-stu-id="ac56a-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ac56a-118">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ac56a-118">Related topics</span></span>

[<span data-ttu-id="ac56a-119">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="ac56a-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)