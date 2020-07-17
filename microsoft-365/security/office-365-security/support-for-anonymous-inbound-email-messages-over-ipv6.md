---
title: Добавление поддержки анонимных входящих писем по протоколу IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать, как настроить поддержку анонимной входящей электронной почты из источников IPv6 в Exchange Online и Exchange Online Protection.
ms.openlocfilehash: fbbcba3631c7b2a7060f07011c119ee973fdf4af
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818713"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="ada2c-103">Добавление поддержки анонимной входящей электронной почты по протоколу IPv6 в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ada2c-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="ada2c-104">Организации Microsoft 365 с почтовыми ящиками Exchange Online и отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online поддерживают анонимную входящую почту через IPv6.</span><span class="sxs-lookup"><span data-stu-id="ada2c-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="ada2c-105">Исходный сервер электронной почты на базе протокола IPv6 должен соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="ada2c-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="ada2c-106">Исходный IPv6-адрес должен иметь действительную обратную запись DNS (PTR), которая позволяет конечному объекту найти доменное имя из IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="ada2c-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="ada2c-107">Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](https://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="ada2c-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="ada2c-108">Прежде чем Организация сможет получить анонимную входящую почту по протоколу IPv6, администратору необходимо обратиться в службу поддержки Майкрософт и запросить ее.</span><span class="sxs-lookup"><span data-stu-id="ada2c-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="ada2c-109">Инструкции по открытию запроса в службу поддержки можно найти в разделе [Contact support for Business Products — Справка для администраторов](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="ada2c-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="ada2c-110">После включения поддержки анонимных входящих сообщений IPv6 в Организации сообщение будет проходить через обычную фильтрацию сообщений, предоставляемую службой.</span><span class="sxs-lookup"><span data-stu-id="ada2c-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ada2c-111">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ada2c-111">Troubleshooting</span></span>

- <span data-ttu-id="ada2c-112">Если исходный сервер электронной почты не имеет записи поиска обратной DNS в IPv6, сообщения будут отклонены со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="ada2c-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="ada2c-113">450 служба 4.7.25 недоступна, отправка IPv6-адреса [2a01:111: F200:2004:: 240] должна иметь обратную запись DNS.</span><span class="sxs-lookup"><span data-stu-id="ada2c-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="ada2c-114">Если отправитель не передает SPF или DKIM проверку подлинности, сообщения будут отклонены со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="ada2c-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="ada2c-115">450 служба 4.7.26 недоступна, сообщение, отправленное по протоколу IPv6 [2a01:111: F200:2004:: 240], должен быть прошел проверку SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="ada2c-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="ada2c-116">Если вы попытаетесь получить анонимные IPv6-сообщения до того, как вы настроили ее, сообщение будет отклонено со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="ada2c-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="ada2c-117">550 5.2.1 служба недоступна, [contoso.com] не принимает сообщения электронной почты по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="ada2c-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ada2c-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ada2c-118">Related topics</span></span>

[<span data-ttu-id="ada2c-119">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="ada2c-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)