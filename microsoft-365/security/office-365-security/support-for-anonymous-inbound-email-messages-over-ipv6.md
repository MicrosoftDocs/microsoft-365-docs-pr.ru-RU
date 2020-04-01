---
title: Добавление поддержки анонимной входящей электронной почты по протоколу IPv6
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
description: Администратор может узнать, как настроить поддержку анонимной входящей электронной почты из источников IPv6 в Exchange Online и Exchange Online Protection.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083645"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="7fb4d-103">Добавление поддержки анонимной входящей электронной почты по протоколу IPv6 в Office 365</span><span class="sxs-lookup"><span data-stu-id="7fb4d-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="7fb4d-104">Организации Office 365 с почтовыми ящиками Exchange Online и отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online поддерживают анонимную входящую почту через IPv6.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="7fb4d-105">Исходный сервер электронной почты на базе протокола IPv6 должен соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="7fb4d-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="7fb4d-106">Исходный IPv6-адрес должен иметь действительную обратную запись DNS (PTR), которая позволяет конечному объекту найти доменное имя из IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="7fb4d-107">Отправитель должен пройти проверку инфраструктуры политики отправителей (определенную в документе [RFC 7208](https://tools.ietf.org/html/rfc7208)) или [проверку DKIM](https://dkim.org/) (которая описана в документе [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="7fb4d-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="7fb4d-108">Прежде чем ваша организация сможет получать анонимную входящую почту по протоколу IPv6, администратору необходимо обратиться в службу поддержки Майкрософт и запросить ее.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="7fb4d-109">Откройте центр администрирования Microsoft 365 <https://admin.microsoft.com/adminportal/home> и щелкните **Справка** (?).</span><span class="sxs-lookup"><span data-stu-id="7fb4d-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="7fb4d-110">**В появившемся всплывающем** меню введите текст с описанием в поле поиска (например, "запрос анонимной входящей IPv6-адреса"), а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="7fb4d-111">В нижней части страницы щелкните службу **поддержки**.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="7fb4d-112">На открывшейся странице **Поддержка контакта** заполните поля и проверьте данные (прокрутите вниз, как необходимо), а затем нажмите кнопку **контакт**.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="7fb4d-113">После включения поддержки анонимных входящих сообщений IPv6 в Организации сообщение будет проходить через обычную фильтрацию сообщений, предоставляемую службой.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7fb4d-114">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="7fb4d-114">Troubleshooting</span></span>

- <span data-ttu-id="7fb4d-115">Если исходный сервер электронной почты не имеет записи поиска обратной DNS в IPv6, сообщения будут отклонены со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="7fb4d-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="7fb4d-116">450 служба 4.7.25 недоступна, отправка IPv6-адреса [2a01:111: F200:2004:: 240] должна иметь обратную запись DNS.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="7fb4d-117">Если отправитель не передает SPF или DKIM проверку подлинности, сообщения будут отклонены со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="7fb4d-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="7fb4d-118">450 служба 4.7.26 недоступна, сообщение, отправленное по протоколу IPv6 [2a01:111: F200:2004:: 240], должен быть прошел проверку SPF или DKIM.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="7fb4d-119">Если вы попытаетесь получить анонимные IPv6-сообщения до того, как вы настроили ее, сообщение будет отклонено со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="7fb4d-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="7fb4d-120">550 5.2.1 служба недоступна, [contoso.com] не принимает сообщения электронной почты по протоколу IPv6.</span><span class="sxs-lookup"><span data-stu-id="7fb4d-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="7fb4d-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7fb4d-121">For more information</span></span>

[<span data-ttu-id="7fb4d-122">Поддержка проверки сообщений, подписанных с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="7fb4d-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
