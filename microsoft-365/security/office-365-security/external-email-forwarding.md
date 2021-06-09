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
ms.openlocfilehash: 6b96d3d656a89e7102550d09a2f5052fdb5ae818
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52792960"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="7c800-103">Управление автоматической внешней отправкой электронной почты в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c800-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7c800-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7c800-104">**Applies to**</span></span>
- [<span data-ttu-id="7c800-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7c800-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7c800-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="7c800-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7c800-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c800-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7c800-108">В качестве администратора у вас могут быть требования к компании, чтобы ограничить или контролировать автоматические переадружаные сообщения внешним получателям (получателям за пределами вашей организации).</span><span class="sxs-lookup"><span data-stu-id="7c800-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="7c800-109">Отправка электронной почты может быть полезной, но может также представлять угрозу безопасности из-за потенциального раскрытия информации.</span><span class="sxs-lookup"><span data-stu-id="7c800-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="7c800-110">Злоумышленники могут использовать эти сведения для атаки на организацию или партнеров.</span><span class="sxs-lookup"><span data-stu-id="7c800-110">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="7c800-111">Следующие типы автоматической переададки доступны в Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="7c800-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="7c800-112">Пользователи могут настроить правила ["Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) для автоматической отправки сообщений внешним отправителям (намеренно или в результате взлома учетной записи).</span><span class="sxs-lookup"><span data-stu-id="7c800-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>
- <span data-ttu-id="7c800-113">Администраторы могут настроить пересылку почтовых ящиков (также известная как _smTP forwarding)_ для автоматической пересылания сообщений внешним получателям. [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="7c800-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="7c800-114">Администратор может выбрать, следует ли просто пересылать сообщения или хранить копии пересылаемого сообщения в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="7c800-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="7c800-115">Вы можете использовать политики исходящие фильтры нежелательной почты для управления автоматической переадружаемой к внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="7c800-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="7c800-116">Доступны три параметра:</span><span class="sxs-lookup"><span data-stu-id="7c800-116">Three settings are available:</span></span>

- <span data-ttu-id="7c800-117">**Автоматическая — система управления:** автоматическая внешняя переадружение блокируется.</span><span class="sxs-lookup"><span data-stu-id="7c800-117">**Automatic - System-controlled**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="7c800-118">Внутренняя автоматическая переададка сообщений будет продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="7c800-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="7c800-119">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c800-119">This is the default setting.</span></span>
- <span data-ttu-id="7c800-120">**On.** Автоматическая внешняя переадружение разрешена и не ограничена.</span><span class="sxs-lookup"><span data-stu-id="7c800-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="7c800-121">**Отключена** автоматическая внешняя переадпортка, в результате чего отправителю отчет о невывозе (также известном как сообщение о NDR или отказов).</span><span class="sxs-lookup"><span data-stu-id="7c800-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="7c800-122">Инструкции по настройке этих параметров см. в инструкции По настройке фильтрации исходящие нежелательной почты [в EOP.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="7c800-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7c800-123">Отключение автоматической переадресации отключает все правила (пользователи) или пересылание почтовых ящиков (администраторов), которые перенаправляют сообщения на внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="7c800-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="7c800-124">Автоматическая переададка сообщений между внутренними пользователями не зависит от параметров в политиках фильтра от нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="7c800-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="7c800-125">Сведения о пользователях, автоматически переадружающих сообщения внешним получателям, можно найти в отчете о автоматических [сообщениях.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="7c800-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="7c800-126">Как параметры политики фильтрации исходящие нежелательной почты работают с другими средствами автоматической переададки электронной почты</span><span class="sxs-lookup"><span data-stu-id="7c800-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="7c800-127">В качестве администратора вы, возможно, уже настроили другие элементы управления, чтобы разрешить или заблокировать автоматическую отправку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7c800-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="7c800-128">Пример.</span><span class="sxs-lookup"><span data-stu-id="7c800-128">For example:</span></span>

- <span data-ttu-id="7c800-129">[Удаленные домены,](/exchange/mail-flow-best-practices/remote-domains/remote-domains) позволяющие или блокируют автоматическую отправку электронной почты в некоторые или все внешние домены.</span><span class="sxs-lookup"><span data-stu-id="7c800-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>
- <span data-ttu-id="7c800-130">Условия и действия в [](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange (также известные как правила транспорта) для обнаружения и блокировки автоматически пересылаемых сообщений внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="7c800-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="7c800-131">Параметры удаленного домена и правила потока почты не зависят от параметров политик фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="7c800-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="7c800-132">Пример.</span><span class="sxs-lookup"><span data-stu-id="7c800-132">For example:</span></span>

- <span data-ttu-id="7c800-133">Вы разрешаете автоматическую переададку для удаленного домена, но блокируете автоматическую переададку в исходящие политики фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="7c800-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="7c800-134">В этом примере автоматически переададные сообщения блокируются.</span><span class="sxs-lookup"><span data-stu-id="7c800-134">In this example, automatically forwarded messages are blocked.</span></span>
- <span data-ttu-id="7c800-135">Вы разрешаете автоматическую пересылку в исходящие политики фильтрации нежелательной почты, но для блокировки автоматически пересылаемой электронной почты используются правила потока почты или параметры удаленного домена.</span><span class="sxs-lookup"><span data-stu-id="7c800-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="7c800-136">В этом примере правила потока почты или параметры удаленного домена будут блокировать автоматически пересылаемые сообщения.</span><span class="sxs-lookup"><span data-stu-id="7c800-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="7c800-137">Независимость этой функции позволяет (например) разрешить автоматическую переадежку в политики фильтра исходящие спама, но использовать удаленные домены для управления внешними доменами, в которые пользователи могут отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="7c800-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="7c800-138">Заблокированные сообщения для переададки электронной почты</span><span class="sxs-lookup"><span data-stu-id="7c800-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="7c800-139">Когда сообщение обнаруживается автоматически, а политика [](configure-the-outbound-spam-policy.md) исходящие фильтры  нежелательной почты блокирует это действие, сообщение возвращается отправителю в NDR, содержадом следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="7c800-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
