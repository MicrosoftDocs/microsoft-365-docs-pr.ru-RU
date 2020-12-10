---
title: Настройка и управление внешним перенаправлением электронной почты, автоматической переадресации, отказ в доступе к 5.7.520, отключению внешней переадресации, администратор отключил внешнюю переадресацию, политику защиты от нежелательной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: bbe341899599d5092db0b0961add5a9825eca3b4
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616600"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="c07b3-103">Управление автоматической переадресацией внешних сообщений электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c07b3-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c07b3-104">Администраторы могут иметь требования к Организации для ограничения или управления автоматически пересылаемыми сообщениями внешним получателям (получателям за пределами организации).</span><span class="sxs-lookup"><span data-stu-id="c07b3-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="c07b3-105">Переадресация электронной почты может быть полезной, но также может представлять угрозу безопасности из-за потенциального разглашения информации.</span><span class="sxs-lookup"><span data-stu-id="c07b3-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="c07b3-106">Злоумышленники могут использовать эти сведения для атаки на вашу организацию или партнеров.</span><span class="sxs-lookup"><span data-stu-id="c07b3-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="c07b3-107">В Microsoft 365 доступны следующие типы автоматической пересылки:</span><span class="sxs-lookup"><span data-stu-id="c07b3-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="c07b3-108">Пользователи могут настраивать [правила для папки "Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) для автоматической пересылки сообщений внешним отправителям (намеренно или в результате скомпрометированной учетной записи).</span><span class="sxs-lookup"><span data-stu-id="c07b3-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="c07b3-109">Администраторы могут настроить [переадресацию почтовых ящиков](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (также называемую _пересылкой SMTP_) для автоматической пересылки сообщений внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="c07b3-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="c07b3-110">Для управления автоматической пересылкой внешним получателям можно использовать политики фильтрации исходящей нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c07b3-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="c07b3-111">Доступны три параметра:</span><span class="sxs-lookup"><span data-stu-id="c07b3-111">Three settings are available:</span></span>

- <span data-ttu-id="c07b3-112">**Автоматический**: Автоматическая внешняя переадресация заблокирована.</span><span class="sxs-lookup"><span data-stu-id="c07b3-112">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="c07b3-113">Внутренняя автоматическая переадресация сообщений будет продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="c07b3-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="c07b3-114">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c07b3-114">This is the default setting.</span></span>

- <span data-ttu-id="c07b3-115">**On**: Автоматическая внешняя переадресация разрешена и не ограничена.</span><span class="sxs-lookup"><span data-stu-id="c07b3-115">**On**: Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="c07b3-116">**Disabled: автоматическая** внешняя переадресация отключена и приведет к отправителю отчета о недоставке (также называемом сообщением о недоставке или сообщении о недоставке).</span><span class="sxs-lookup"><span data-stu-id="c07b3-116">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="c07b3-117">Инструкции по настройке этих параметров приведены [в статье Настройка фильтрации исходящих нежелательных сообщений в EOP](configure-the-outbound-spam-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c07b3-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c07b3-118">При отключении автоматической пересылки отключаются все правила (пользователи) или пересылка почтовых ящиков (Администраторы), перенаправляющие сообщения на внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="c07b3-118">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="c07b3-119">Параметры политик фильтрации нежелательной почты не влияют на автоматическую пересылку сообщений между внутренними пользователями.</span><span class="sxs-lookup"><span data-stu-id="c07b3-119">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="c07b3-120">Вы можете просмотреть сведения о пользователях, которые автоматически пересылают сообщения внешним получателям в [отчете о автоматически пересылаемых сообщениях](mfi-auto-forwarded-messages-report.md).</span><span class="sxs-lookup"><span data-stu-id="c07b3-120">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="c07b3-121">Как параметры политики фильтрации нежелательной почты работают с другими элементами управления автоматической переадресации электронной почты</span><span class="sxs-lookup"><span data-stu-id="c07b3-121">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="c07b3-122">Администратор может уже настроить другие элементы управления, чтобы разрешить или заблокировать автоматическую переадресацию электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c07b3-122">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="c07b3-123">Например,</span><span class="sxs-lookup"><span data-stu-id="c07b3-123">For example:</span></span>

- <span data-ttu-id="c07b3-124">[Удаленные домены](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) , чтобы разрешить или заблокировать автоматическую пересылку электронной почты некоторым или всем внешним доменам.</span><span class="sxs-lookup"><span data-stu-id="c07b3-124">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="c07b3-125">Условия и действия в [правилах для почтовых ящиков](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange (также называемых правилами транспорта) позволяют обнаруживать и блокировать автоматически переадресованные сообщения внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="c07b3-125">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="c07b3-126">Параметры удаленного домена и правила обработки почтового ящика не зависят от параметров в политиках фильтрации исходящих нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c07b3-126">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="c07b3-127">Например,</span><span class="sxs-lookup"><span data-stu-id="c07b3-127">For example:</span></span>

- <span data-ttu-id="c07b3-128">Вы разрешаете автоматическую пересылку для удаленного домена, но блокируете автоматическую пересылку в политиках фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="c07b3-128">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="c07b3-129">В этом примере автоматически перенаправляемые сообщения блокируются.</span><span class="sxs-lookup"><span data-stu-id="c07b3-129">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="c07b3-130">Разрешается автоматическая пересылка в политиках фильтрации нежелательной почты, но для блокировки автоматически пересылаемых сообщений используются правила обработки почты или параметры удаленного домена.</span><span class="sxs-lookup"><span data-stu-id="c07b3-130">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="c07b3-131">В этом примере правила обработки почтового процесса или параметры удаленного домена блокируют автоматически перенаправляемые сообщения.</span><span class="sxs-lookup"><span data-stu-id="c07b3-131">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="c07b3-132">Эта функциональная возможность позволяет (например,) разрешить автоматическую пересылку в политиках фильтрации нежелательной почты, но использовать удаленные домены для управления внешними доменами, на которые пользователи могут пересылать сообщения.</span><span class="sxs-lookup"><span data-stu-id="c07b3-132">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="c07b3-133">Сообщение о перенаправлении заблокированной электронной почты</span><span class="sxs-lookup"><span data-stu-id="c07b3-133">The blocked email forwarding message</span></span>

<span data-ttu-id="c07b3-134">Если сообщение обнаруживается как автоматически перенаправляемое, а политика Организации *блокирует* эту операцию, сообщение возвращается отправителю в отчете о недоставке, который содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="c07b3-134">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
