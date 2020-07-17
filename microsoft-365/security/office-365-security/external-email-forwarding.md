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
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080117"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="4e4d5-103">Настройка переадресации внешних сообщений электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="4e4d5-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="4e4d5-104">Внешняя переадресация контролируется с помощью *политики исходящей нежелательной почты* и ограничивается пользователями в соответствии с настроенным параметром.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="4e4d5-105">Сейчас поддерживаются три параметра:</span><span class="sxs-lookup"><span data-stu-id="4e4d5-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="4e4d5-106">**Автоматический** — в этом режиме система несет ответственность за принятие решения о том, разрешено ли переадресованное сообщение.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="4e4d5-107">Это режим по умолчанию, и в этом режиме система блокирует автоматическую внешнюю переадресацию.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="4e4d5-108">**Включено** — Автоматическая внешняя переадресация разрешена и не ограничена.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="4e4d5-109">**Выкл** . — Автоматическая внешняя переадресация отключена, и для конечного пользователя будет получен отчет о недоставке (NDR).</span><span class="sxs-lookup"><span data-stu-id="4e4d5-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="4e4d5-110">Подробнее о настройке этих параметров можно узнать [в статье Настройка фильтрации исходящих нежелательных сообщений в EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="4e4d5-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="4e4d5-111">Управление переадресацией внешних сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e4d5-111">Controlling external email forwarding</span></span>

<span data-ttu-id="4e4d5-112">Администраторы организации могут иметь требования к Организации для ограничения или управления тем, кто может автоматически пересылать сообщения электронной почты с помощью правил папки "Входящие" или пересылки SMTP, за преноски.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="4e4d5-113">Переадресация электронной почты может быть полезной, но она также может представлять риск, используя потенциально раскрытие информации, даже предоставляя злоумышленникам информацию, которая может быть использована для атаки на организацию или ее партнеров.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="4e4d5-114">Office 365 не поддерживает автоматическое перенаправление внешней переадресации правилами папки "Входящие" или конфигурацией почтового ящика, которое обеспечивает безопасную политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="4e4d5-115">Тем не менее, администратор может изменить эти параметры для всех или некоторых пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="4e4d5-116">На пересылку сообщений между внутренними пользователями не влияют такие изменения.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="4e4d5-117">Отключение автоматической пересылки к внешним адресам в Office 365 выполняется по этапам с подробностями, связанными с помощью posts в [сообщениях центра сообщений](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="4e4d5-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="4e4d5-118">Чтобы помочь администраторам подготовиться к этим изменениям, необходимо заранее изменить политики, чтобы убедиться в отсутствии нарушений их почтовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="4e4d5-119">Дополнительные сведения о пользователях, которые используют автоматическую пересылку (правила для папки "Входящие" или переадресацию SMTP) в Организации, можно найти в [отчете о автоматических пересылаемых сообщениях](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4e4d5-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="4e4d5-120">Сообщение о перенаправлении заблокированной электронной почты</span><span class="sxs-lookup"><span data-stu-id="4e4d5-120">The blocked email forwarding message</span></span>

<span data-ttu-id="4e4d5-121">Если сообщение обнаруживается как автоматически перенаправляемое, а политика Организации *блокирует* , что в конечный пользователь будет создан **отчет о недоставке** .</span><span class="sxs-lookup"><span data-stu-id="4e4d5-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="4e4d5-122">Отчет указывает на то, что сообщение не было доставлено.</span><span class="sxs-lookup"><span data-stu-id="4e4d5-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="4e4d5-123">Отчет о недоставке будет иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="4e4d5-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
