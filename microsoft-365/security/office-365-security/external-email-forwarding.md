---
title: Настройка и управление внешней переадминационной почтой, автоматическая переадружение, отказ в доступе 5.7.520, отключение внешней переадправления. Администратор отключил внешнюю переадминику, политику нежелательной почты для исходящие сообщений
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
ms.openlocfilehash: e578cadf6687e02c900299a75bdd00a9d6e5b2ee
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166151"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="14394-103">Управление автоматической переадружаемой внешней электронной почтой в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14394-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="14394-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="14394-104">**Applies to**</span></span>
- [<span data-ttu-id="14394-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="14394-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="14394-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="14394-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="14394-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14394-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="14394-108">Как администратор вы можете предъявлять требования компании, чтобы ограничить или контролировать автоматически переадружаемую сообщения внешним получателям (получателям за пределами организации).</span><span class="sxs-lookup"><span data-stu-id="14394-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="14394-109">Переадения электронной почты может быть полезной, но также может представлять угрозу безопасности из-за возможного раскрытия информации.</span><span class="sxs-lookup"><span data-stu-id="14394-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="14394-110">Злоумышленники могут использовать эту информацию для атаки на вашу организацию или партнеров.</span><span class="sxs-lookup"><span data-stu-id="14394-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="14394-111">В Microsoft 365 доступны следующие типы автоматической переад вперед:</span><span class="sxs-lookup"><span data-stu-id="14394-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="14394-112">Пользователи могут [настраивать](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) правила для входящих сообщений для автоматической перенаправки сообщений внешним отправителям (намеренно или в результате компрометации учетной записи).</span><span class="sxs-lookup"><span data-stu-id="14394-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="14394-113">Администраторы могут настроить переадружение почтовых ящиков [(также](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) известное как пересылание _SMTP)_ для автоматической пересылки сообщений внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="14394-113">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="14394-114">Администратор может выбрать, нужно ли просто переадад часть сообщений или хранить их копии в почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="14394-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="14394-115">Политики фильтрации исходящие нежелательной почты можно использовать для управления автоматической переадружаемой почтой внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="14394-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="14394-116">Доступны три параметра:</span><span class="sxs-lookup"><span data-stu-id="14394-116">Three settings are available:</span></span>

- <span data-ttu-id="14394-117">**Автоматическая:** автоматическая внешняя переадружение заблокирована.</span><span class="sxs-lookup"><span data-stu-id="14394-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="14394-118">Внутренняя автоматическая переададка сообщений продолжит работать.</span><span class="sxs-lookup"><span data-stu-id="14394-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="14394-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14394-119">This is the default setting.</span></span>
- <span data-ttu-id="14394-120">**On:** Automatic external forwarding is allowed and not restricted.</span><span class="sxs-lookup"><span data-stu-id="14394-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="14394-121">**Отключено:** автоматическая внешняя переадружение отключена и приведет к отправке отчета о доставке (также известного как сообщение о возврате) отправителю.</span><span class="sxs-lookup"><span data-stu-id="14394-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="14394-122">Инструкции по настройке этих параметров см. в подстройке "Настройка фильтрации исходящие нежелательных [сообщений" в EOP.](configure-the-outbound-spam-policy.md)</span><span class="sxs-lookup"><span data-stu-id="14394-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="14394-123">Отключение автоматической пересылки отключает все правила для входящих сообщений (пользователей) или переадресации почтовых ящиков (администраторов), которые перенаправляют сообщения на внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="14394-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="14394-124">Параметры политик фильтрации исходящие нежелательной почты не влияют на автоматическую переадновку сообщений между внутренними пользователями.</span><span class="sxs-lookup"><span data-stu-id="14394-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="14394-125">Сведения о пользователях, которые автоматически переадружат сообщения внешним получателям, см. в отчете о [автоматически переадружаемом сообщении.](mfi-auto-forwarded-messages-report.md)</span><span class="sxs-lookup"><span data-stu-id="14394-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="14394-126">Как параметры политики фильтрации исходящие нежелательной почты работают с другими автоматическими средствами управления переададантами электронной почты</span><span class="sxs-lookup"><span data-stu-id="14394-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="14394-127">Возможно, вы как администратор уже настроили другие элементы управления, чтобы разрешить или заблокировать автоматическую переадновку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="14394-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="14394-128">Например:</span><span class="sxs-lookup"><span data-stu-id="14394-128">For example:</span></span>

- <span data-ttu-id="14394-129">[Удаленные домены,](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) позволяющие разрешить или заблокировать автоматическую переадружение электронной почты на некоторые или все внешние домены.</span><span class="sxs-lookup"><span data-stu-id="14394-129">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="14394-130">Условия и действия в [правилах](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) потока почты Exchange (также известные как правила транспорта) для обнаружения и блокировки автоматически пересылаемых сообщений внешним получателям.</span><span class="sxs-lookup"><span data-stu-id="14394-130">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="14394-131">Параметры удаленного домена и правила потока почты не зависят от параметров в политиках фильтрации исходящие спама.</span><span class="sxs-lookup"><span data-stu-id="14394-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="14394-132">Например:</span><span class="sxs-lookup"><span data-stu-id="14394-132">For example:</span></span>

- <span data-ttu-id="14394-133">Вы разрешаете автоматическую переадновку для удаленного домена, но блокируете ее в политиках фильтрации исходящие нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="14394-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="14394-134">В этом примере автоматически переадновимые сообщения блокируются.</span><span class="sxs-lookup"><span data-stu-id="14394-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="14394-135">Вы разрешаете автоматическую пересылку в политиках фильтрации исходящие нежелательной почты, но для блокировки автоматически пересылаемой электронной почты используются правила потока почты или параметры удаленного домена.</span><span class="sxs-lookup"><span data-stu-id="14394-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="14394-136">В этом примере правила потока почты или параметры удаленного домена блокируют автоматически пересылаемую почту.</span><span class="sxs-lookup"><span data-stu-id="14394-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="14394-137">Эта независимость функций позволяет (например) разрешить автоматическую переадружение в политиках фильтрации исходящие спама, но использовать удаленные домены для управления внешними доменами, на которые пользователи могут переадружить сообщения.</span><span class="sxs-lookup"><span data-stu-id="14394-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="14394-138">Заблокированное сообщение для переададатора электронной почты</span><span class="sxs-lookup"><span data-stu-id="14394-138">The blocked email forwarding message</span></span>

<span data-ttu-id="14394-139">Если сообщение обнаруживается как автоматически переадправленное,  а политика организации блокирует это действие, сообщение возвращается отправителю в NDR, содержачем следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="14394-139">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
