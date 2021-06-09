---
title: Подтверждение уведомления об удержании
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать Advanced eDiscovery для отправки и отслеживания юридических уведомлений о удержании по электронной почте, а также мониторинга состояния обязательств.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034889"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="3506b-103">Подтверждение уведомления об удержании</span><span class="sxs-lookup"><span data-stu-id="3506b-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="3506b-104">При ответе на нормативный запрос или расследование может потребоваться информировать хранителей об их обязательствах по сохранению сведений, хранимых в электронном виде (ESI) и любых материалов, которые могут иметь отношение к активному или неизбежному юридическому вопросу.</span><span class="sxs-lookup"><span data-stu-id="3506b-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="3506b-105">При отправлении юридические группы должны знать, что каждый хранитель получал, читал, понимал и соглашался следовать заданным инструкциям.</span><span class="sxs-lookup"><span data-stu-id="3506b-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="3506b-106">Чтобы сократить время, затраты и усилия по совместной работе с хранителями, Advanced eDiscovery позволяет отправлять и выполнять уведомления о удержании по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="3506b-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="3506b-107">Помимо уведомлений по электронной почте, каждый хранитель будет иметь доступ к индивидуализированному порталу соответствия требованиям, что позволяет хранителям получать информацию об изменениях в их состоянии обязательств.</span><span class="sxs-lookup"><span data-stu-id="3506b-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="3506b-108">Уведомления по электронной почте</span><span class="sxs-lookup"><span data-stu-id="3506b-108">Email notifications</span></span>

<span data-ttu-id="3506b-109">После получения уведомления о юридическом удержании каждый хранитель получает уникальное и персонализированное письмо, содержащее определенное уведомление о юридическом удержании и добавленные инструкции.</span><span class="sxs-lookup"><span data-stu-id="3506b-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="3506b-110">Узнайте, как использовать встроенный [](using-communications-editor.md) редактор связи, чтобы разрешить хранителям получать уведомление или получать доступ к порталу соответствия требованиям непосредственно из электронной почты.</span><span class="sxs-lookup"><span data-stu-id="3506b-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="3506b-111">В зависимости от конфигурации уведомления о легальном удержании ваши хранители могут получать следующие уведомления:</span><span class="sxs-lookup"><span data-stu-id="3506b-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="3506b-112">**Уведомление о выдаче:** Первое уведомление, отправлено вашему хранителу.</span><span class="sxs-lookup"><span data-stu-id="3506b-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="3506b-113">В этом уведомлении будут содержаться инструкции по выдаче и уведомление о удержании, приданное к концу сообщения.</span><span class="sxs-lookup"><span data-stu-id="3506b-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="3506b-114">**Уведомление о напоминаниях:** Если включено, уведомление о напоминаниях будет отправлено хранителям в зависимости от указанной частоты и интервала.</span><span class="sxs-lookup"><span data-stu-id="3506b-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="3506b-115">Напоминания будут по-прежнему отправлены либо до тех пор, пока хранитель не подавит уведомление, либо до тех пор, пока количество напоминаний не будет исчерпано.</span><span class="sxs-lookup"><span data-stu-id="3506b-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="3506b-116">**Уведомление об эскалации:** Если включено, уведомление об эскалации будет отправлено вашему хранителу и его руководителю после исчерпания уведомлений о напоминаниях.</span><span class="sxs-lookup"><span data-stu-id="3506b-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="3506b-117">Система автоматически отправляет уведомления об эскалации до завершения указанного числа эскалаций или до тех пор, пока хранитель не подтвердит уведомление о удержании.</span><span class="sxs-lookup"><span data-stu-id="3506b-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="3506b-118">**Уведомление о переоцене:** В ходе расследования, если содержимое уведомления о удержании будет обновлено, обновленное уведомление автоматически будет отправлено хранителю.</span><span class="sxs-lookup"><span data-stu-id="3506b-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="3506b-119">**Уведомление об освобождении:** Когда хранитель освобождается из дела, им будет отправлено уведомление об освобождении.</span><span class="sxs-lookup"><span data-stu-id="3506b-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="3506b-120">Портал соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="3506b-120">Compliance Portal</span></span>

<span data-ttu-id="3506b-121">Помимо уведомлений по электронной почте каждый хранитель будет иметь доступ к уникальному порталу соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3506b-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="3506b-122">Через портал каждый хранитель может просматривать, получать доступ и подтверждать свои активные уведомления о удержании.</span><span class="sxs-lookup"><span data-stu-id="3506b-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Портал соответствия требованиям для хранителя](../media/CustodianPortal.jpg)
