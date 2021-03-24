---
title: Настройка и управление внешней перенаправлением электронной почты, автоматическая переададка, отказано в доступе 5.7.520, отключение внешней переадправления, администратор отключил внешнюю переадправление, исходящие политики по борьбе со спамом
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071445"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="a6fdd-103">Управление автоматической внешней отправкой электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a6fdd-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a6fdd-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="a6fdd-104">**Applies to**</span></span>
- [<span data-ttu-id="a6fdd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a6fdd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a6fdd-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="a6fdd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a6fdd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6fdd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a6fdd-108">В качестве администратора у вас могут быть требования к компании, чтобы ограничить или контролировать автоматические переадружаные сообщения внешним получателям (получателям за пределами вашей организации).</span><span class="sxs-lookup"><span data-stu-id="a6fdd-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="a6fdd-109">Отправка электронной почты может быть полезной, но может также представлять угрозу безопасности из-за потенциального раскрытия информации.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="a6fdd-110">Злоумышленники могут использовать эти сведения для атаки на организацию или партнеров.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="a6fdd-111">В Microsoft 365 доступны следующие типы автоматической переададки:</span><span class="sxs-lookup"><span data-stu-id="a6fdd-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="a6fdd-112">Пользователи могут настроить правила ["Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) для автоматической отправки сообщений внешним отправителям (намеренно или в результате взлома учетной записи).</span><span class="sxs-lookup"><span data-stu-id="a6fdd-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="a6fdd-113">Администраторы могут настроить пересылку почтовых ящиков (также известная как _smTP forwarding)_ для автоматической пересылания сообщений внешним получателям. [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="a6fdd-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="a6fdd-114">Администратор может выбрать, следует ли просто пересылать сообщения или хранить копии пересылаемого сообщения в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="a6fdd-115">Вы можете использовать политики исходящие фильтры нежелательной почты для управления автоматической переадружаемой к внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="a6fdd-116">Доступны три параметра:</span><span class="sxs-lookup"><span data-stu-id="a6fdd-116">Three settings are available:</span></span>

- <span data-ttu-id="a6fdd-117">**Автоматическая.** Автоматическая внешняя переадружение блокируется.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="a6fdd-118">Внутренняя автоматическая переададка сообщений будет продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="a6fdd-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-119">This is the default setting.</span></span>
- <span data-ttu-id="a6fdd-120">**On.** Автоматическая внешняя переадружение разрешена и не ограничена.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="a6fdd-121">**Отключена** автоматическая внешняя переадпортка, в результате чего отправителю отчет о невывозе (также известном как сообщение о NDR или отказов).</span><span class="sxs-lookup"><span data-stu-id="a6fdd-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="a6fdd-122">Инструкции по настройке этих параметров см. в инструкции По настройке фильтрации исходящие нежелательной почты [в EOP.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="a6fdd-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="a6fdd-123">Отключение автоматической переадресации отключает все правила (пользователи) или пересылание почтовых ящиков (администраторов), которые перенаправляют сообщения на внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="a6fdd-124">Автоматическая переададка сообщений между внутренними пользователями не зависит от параметров в политиках фильтра от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="a6fdd-125">Сведения о пользователях, автоматически переадружающих сообщения внешним получателям, можно найти в отчете о автоматических [сообщениях.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="a6fdd-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="a6fdd-126">Как параметры политики фильтрации исходящие нежелательной почты работают с другими средствами автоматической переададки электронной почты</span><span class="sxs-lookup"><span data-stu-id="a6fdd-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="a6fdd-127">В качестве администратора вы, возможно, уже настроили другие элементы управления, чтобы разрешить или заблокировать автоматическую отправку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="a6fdd-128">Пример.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-128">For example:</span></span>

- <span data-ttu-id="a6fdd-129">[Удаленные домены,](/exchange/mail-flow-best-practices/remote-domains/remote-domains) позволяющие или блокируют автоматическую отправку электронной почты в некоторые или все внешние домены.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="a6fdd-130">Условия и действия в [правилах](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) потока почты Exchange (также известные как правила транспорта) для обнаружения и блокировки автоматически пересылаемых сообщений внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="a6fdd-131">Параметры удаленного домена и правила потока почты не зависят от параметров политик фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="a6fdd-132">Пример.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-132">For example:</span></span>

- <span data-ttu-id="a6fdd-133">Вы разрешаете автоматическую переададку для удаленного домена, но блокируете автоматическую переададку в исходящие политики фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="a6fdd-134">В этом примере автоматически переададные сообщения блокируются.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="a6fdd-135">Вы разрешаете автоматическую пересылку в исходящие политики фильтрации нежелательной почты, но для блокировки автоматически пересылаемой электронной почты используются правила потока почты или параметры удаленного домена.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="a6fdd-136">В этом примере правила потока почты или параметры удаленного домена будут блокировать автоматически пересылаемые сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="a6fdd-137">Независимость этой функции позволяет (например) разрешить автоматическую переадежку в политики фильтра исходящие спама, но использовать удаленные домены для управления внешними доменами, в которые пользователи могут отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6fdd-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="a6fdd-138">Заблокированные сообщения для переададки электронной почты</span><span class="sxs-lookup"><span data-stu-id="a6fdd-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="a6fdd-139">Когда сообщение обнаруживается автоматически, а политика [](configure-the-outbound-spam-policy.md) исходящие фильтры  нежелательной почты блокирует это действие, сообщение возвращается отправителю в NDR, содержадом следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="a6fdd-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`