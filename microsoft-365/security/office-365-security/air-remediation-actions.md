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
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955537"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="67c8d-104">Действия по исправлению, следующие за автоматическим исследованием в Office 365</span><span class="sxs-lookup"><span data-stu-id="67c8d-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="67c8d-105">Действия по исправлению</span><span class="sxs-lookup"><span data-stu-id="67c8d-105">Remediation actions</span></span>

<span data-ttu-id="67c8d-106">[Автоматизированное исследование и возможности реагирования](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) в [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 включают некоторые действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="67c8d-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="67c8d-107">При каждом запуске или завершении автоматического исследования обычно отображается одно или несколько действий по исправлению, требующих утверждения командой "Управление операциями безопасности" для продолжения.</span><span class="sxs-lookup"><span data-stu-id="67c8d-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="67c8d-108">В следующей таблице приведены действия по исправлению, которые в настоящее время доступны в Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="67c8d-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="67c8d-109">Действие</span><span class="sxs-lookup"><span data-stu-id="67c8d-109">Action</span></span> | <span data-ttu-id="67c8d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="67c8d-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="67c8d-111">Блокирование URL-адреса (во время щелчка)</span><span class="sxs-lookup"><span data-stu-id="67c8d-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="67c8d-112">Защищает от сообщений электронной почты и документов, содержащих вредоносные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="67c8d-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="67c8d-113">Это позволяет блокировать вредоносные ссылки и связанные с ней веб-страницы, используя [безопасные ссылки](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) , когда пользователь щелкает ссылку в существующем файле Office или в старом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="67c8d-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="67c8d-114">Обратимое удаление электронной почты</span><span class="sxs-lookup"><span data-stu-id="67c8d-114">Soft delete email</span></span>  |<span data-ttu-id="67c8d-115">Обратимое удаление определенных сообщений электронной почты из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="67c8d-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="67c8d-116">Обратимо удаленное сообщение перемещается в папку "элементы с возможностью восстановления" пользователя и сохраняется до истечения срока хранения удаленных элементов.</span><span class="sxs-lookup"><span data-stu-id="67c8d-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="67c8d-117">Обратимое удаление кластеров электронной почты</span><span class="sxs-lookup"><span data-stu-id="67c8d-117">Soft delete email clusters</span></span>  |<span data-ttu-id="67c8d-118">Обратимое удаление вредоносных сообщений электронной почты, которые отвечают на запрос из всех почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="67c8d-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="67c8d-119">Обратимо удаленные сообщения перемещаются в папку "элементы с возможностью восстановления" пользователями и сохраняются до истечения срока хранения удаленных элементов.</span><span class="sxs-lookup"><span data-stu-id="67c8d-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="67c8d-120">Отключение внешней переадресации почты</span><span class="sxs-lookup"><span data-stu-id="67c8d-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="67c8d-121">Удаляет правило пересылки из почтового ящика конкретного конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="67c8d-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="67c8d-122">В Office 365 ATP никакие действия по исправлению не выполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="67c8d-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="67c8d-123">Действия по исправлению принимаются только при утверждении группой безопасности Организации.</span><span class="sxs-lookup"><span data-stu-id="67c8d-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="67c8d-124">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="67c8d-124">Next steps</span></span>

- [<span data-ttu-id="67c8d-125">Просмотр ожидающих или завершенных действий по исправлению, следующих за автоматическим исследованием в Office 365</span><span class="sxs-lookup"><span data-stu-id="67c8d-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="67c8d-126">Сведения и результаты автоматического исследования в Office 365</span><span class="sxs-lookup"><span data-stu-id="67c8d-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="67c8d-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="67c8d-127">Related articles</span></span>

- [<span data-ttu-id="67c8d-128">Автоматическое исследование в Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="67c8d-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="67c8d-129">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="67c8d-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)