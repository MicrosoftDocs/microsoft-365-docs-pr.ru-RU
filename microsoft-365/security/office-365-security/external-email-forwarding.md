---
title: Настройка и управление внешним перенаправлением электронной почты, автоматической переадресации, отказ в доступе к 5.7.520, отключению внешней переадресации, администратор отключил внешнюю переадресацию, политику защиты от нежелательной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f729aa816caf8fb07499037ee27fbfc37b7205b3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202883"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="680cf-103">Настройка переадресации внешних сообщений электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="680cf-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="680cf-104">Внешняя переадресация контролируется с помощью *политики исходящей нежелательной почты* и ограничивается пользователями в соответствии с настроенным параметром.</span><span class="sxs-lookup"><span data-stu-id="680cf-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="680cf-105">Сейчас поддерживаются три параметра:</span><span class="sxs-lookup"><span data-stu-id="680cf-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="680cf-106">**Автоматический** — в этом режиме система несет ответственность за принятие решения о том, разрешено ли переадресованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="680cf-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="680cf-107">Это режим по умолчанию, и в этом режиме система блокирует автоматическую внешнюю переадресацию.</span><span class="sxs-lookup"><span data-stu-id="680cf-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="680cf-108">**Включено** — Автоматическая внешняя переадресация разрешена и не ограничена.</span><span class="sxs-lookup"><span data-stu-id="680cf-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="680cf-109">**Выкл** . — Автоматическая внешняя переадресация отключена, и для конечного пользователя будет получен отчет о недоставке (NDR).</span><span class="sxs-lookup"><span data-stu-id="680cf-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="680cf-110">Подробнее о настройке этих параметров можно узнать [в статье Настройка фильтрации исходящих нежелательных сообщений в EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .</span><span class="sxs-lookup"><span data-stu-id="680cf-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="680cf-111">При отключении автоматической пересылки будут также дсабле правила для папки "Входящие", перенаправляющие сообщения на внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="680cf-111">Disabling automatic forwarding will also dsable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="680cf-112">Управление переадресацией внешних сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="680cf-112">Controlling external email forwarding</span></span>

<span data-ttu-id="680cf-113">Администраторы организации могут иметь требования к Организации для ограничения или управления тем, кто может автоматически пересылать сообщения электронной почты с помощью правил папки "Входящие" или пересылки SMTP, за преноски.</span><span class="sxs-lookup"><span data-stu-id="680cf-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="680cf-114">Переадресация электронной почты может быть полезной, но она также может представлять риск, используя потенциально раскрытие информации, даже предоставляя злоумышленникам информацию, которая может быть использована для атаки на организацию или ее партнеров.</span><span class="sxs-lookup"><span data-stu-id="680cf-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="680cf-115">Office 365 не поддерживает автоматическое перенаправление внешней переадресации правилами папки "Входящие" или конфигурацией почтового ящика, которое обеспечивает безопасную политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="680cf-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="680cf-116">Тем не менее, администратор может изменить эти параметры для всех или некоторых пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="680cf-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="680cf-117">На пересылку сообщений между внутренними пользователями не влияют такие изменения.</span><span class="sxs-lookup"><span data-stu-id="680cf-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="680cf-118">Отключение автоматической пересылки к внешним адресам в Office 365 выполняется по этапам с подробностями, связанными с помощью posts в [сообщениях центра сообщений](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="680cf-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="680cf-119">Чтобы помочь администраторам подготовиться к этим изменениям, необходимо заранее изменить политики, чтобы убедиться в отсутствии нарушений их почтовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="680cf-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="680cf-120">Дополнительные сведения о пользователях, которые используют автоматическую пересылку (правила для папки "Входящие" или переадресацию SMTP) в Организации, можно найти в [отчете о автоматических пересылаемых сообщениях](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="680cf-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="680cf-121">Как эта политика работает с другими элементами управления автоматической пересылки</span><span class="sxs-lookup"><span data-stu-id="680cf-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="680cf-122">Как администратор, у вас уже могут быть другие типы элементов управления, например, блокировка автоматической пересылки в [удаленных доменах](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) и использование правила транспорта Exchange (ETR).</span><span class="sxs-lookup"><span data-stu-id="680cf-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="680cf-123">Оба эти элемента управления не зависят от этой конкретной функции, например, если разрешить автоматическую пересылку для удаленного домена, но блокировать автоматическую переадресацию с помощью политики исходящих нежелательных сообщений результат будет блокироваться автоматически перенаправленным сообщением.</span><span class="sxs-lookup"><span data-stu-id="680cf-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="680cf-124">Аналогично, если вы разрешите автоматическую пересылку в политике исходящих нежелательной почты, но блокируете ее в ETR или удаленном домене, сообщение будет заблокировано одним из этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="680cf-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="680cf-125">Это позволяет, например, разрешить автоматическую пересылку в политике исходящей почты и использовать удаленные домены для управления доменами, на которые пользователи могут автоматически пересылать сообщения.</span><span class="sxs-lookup"><span data-stu-id="680cf-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="680cf-126">Сообщение о перенаправлении заблокированной электронной почты</span><span class="sxs-lookup"><span data-stu-id="680cf-126">The blocked email forwarding message</span></span>

<span data-ttu-id="680cf-127">Если сообщение обнаруживается как автоматически перенаправляемое, а политика Организации *блокирует* , что в конечный пользователь будет создан **отчет о недоставке** .</span><span class="sxs-lookup"><span data-stu-id="680cf-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="680cf-128">Отчет указывает на то, что сообщение не было доставлено.</span><span class="sxs-lookup"><span data-stu-id="680cf-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="680cf-129">Отчет о недоставке будет иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="680cf-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
