---
title: Действия по исправлению в Office 365 автоматизированное исследование и ответ
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Сведения о действиях по исправлению в автоматическом расследовании и возможностях реагирования в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 0db49a28fb90bcddcdd874ac54216957e4be5fa1
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288517"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="fe46e-104">Действия по исправлению, следующие за автоматическим исследованием в Office 365</span><span class="sxs-lookup"><span data-stu-id="fe46e-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="fe46e-105">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="fe46e-105">Remediation actions</span></span>

<span data-ttu-id="fe46e-106">[Автоматизированные функции расследования и реагирования](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) в Office 365 Advanced Threat protection включают некоторые действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="fe46e-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="fe46e-107">При каждом запуске или завершении автоматического исследования обычно отображается одно или несколько действий по исправлению, требующих утверждения командой "Управление операциями безопасности" для продолжения.</span><span class="sxs-lookup"><span data-stu-id="fe46e-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="fe46e-108">В следующей таблице приведены действия по исправлению, которые в настоящее время доступны в [Office 365 Advanced Threat protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="fe46e-108">The following table summarizes remediation actions currently available in [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> 

|<span data-ttu-id="fe46e-109">Действие</span><span class="sxs-lookup"><span data-stu-id="fe46e-109">Action</span></span> | <span data-ttu-id="fe46e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fe46e-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="fe46e-111">Блокирование URL-адреса (во время щелчка)</span><span class="sxs-lookup"><span data-stu-id="fe46e-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="fe46e-112">Защита от сообщений электронной почты и документов, содержащих вредоносные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="fe46e-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="fe46e-113">Это позволяет блокировать вредоносные ссылки и связанные с ней веб-страницы, используя [безопасные ссылки](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) , когда пользователь щелкает ссылку в существующем файле Office или в старом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="fe46e-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="fe46e-114">Обратимое удаление электронной почты</span><span class="sxs-lookup"><span data-stu-id="fe46e-114">Soft delete email</span></span>  |<span data-ttu-id="fe46e-115">Обратимое удаление определенных сообщений электронной почты из почтового ящика пользователя</span><span class="sxs-lookup"><span data-stu-id="fe46e-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="fe46e-116">Обратимое удаление кластеров электронной почты</span><span class="sxs-lookup"><span data-stu-id="fe46e-116">Soft delete email clusters</span></span>  |<span data-ttu-id="fe46e-117">Обратимое удаление вредоносных сообщений электронной почты, отвечающих запросу из почтовых ящиков всех пользователей</span><span class="sxs-lookup"><span data-stu-id="fe46e-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="fe46e-118">Отключение внешней переадресации почты</span><span class="sxs-lookup"><span data-stu-id="fe46e-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="fe46e-119">Удаление правила пересылки из определенного почтового ящика пользователя</span><span class="sxs-lookup"><span data-stu-id="fe46e-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="fe46e-120">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="fe46e-120">Approve (or reject) pending actions</span></span>

![Страница "действия по расследованию воздуха"](../../media/air-investigationactionspage.png)

<span data-ttu-id="fe46e-122">При просмотре [сведений об исследовании](air-view-investigation-results.md)вы можете утвердить или отклонить все ожидающие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="fe46e-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="fe46e-123">Мы рекомендуем сделать это как можно скорее, чтобы завершить автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="fe46e-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe46e-124">Для утверждения или отклонения действий по исправлению необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="fe46e-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="fe46e-125">Ознакомьтесь [с разрешениями, необходимыми для использования возможностей Air](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="fe46e-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="fe46e-126">Перейдите на вкладку **действия** .</span><span class="sxs-lookup"><span data-stu-id="fe46e-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="fe46e-127">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="fe46e-127">Select an item in the list.</span></span> <span data-ttu-id="fe46e-128">(При этом становятся активными кнопки утвердить и отклонить.)</span><span class="sxs-lookup"><span data-stu-id="fe46e-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="fe46e-129">Просмотрите доступные сведения о выбранных элементах, а затем либо утвердите, либо отклоните действия.</span><span class="sxs-lookup"><span data-stu-id="fe46e-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="fe46e-130">**Одобрить** разрешает запуск исправления.</span><span class="sxs-lookup"><span data-stu-id="fe46e-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="fe46e-131">**Отклонить** не предпринимать дальнейших действий</span><span class="sxs-lookup"><span data-stu-id="fe46e-131">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe46e-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fe46e-132">Next steps</span></span>

- [<span data-ttu-id="fe46e-133">Сведения о скомпрометированном пользователе безопасности стратегия</span><span class="sxs-lookup"><span data-stu-id="fe46e-133">Learn about the compromised user security playbook</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [<span data-ttu-id="fe46e-134">Просмотр отчетов ATP</span><span class="sxs-lookup"><span data-stu-id="fe46e-134">View your ATP reports</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)