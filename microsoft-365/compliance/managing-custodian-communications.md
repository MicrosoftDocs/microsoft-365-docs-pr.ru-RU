---
title: Работа с коммуникациями в Advanced eDiscovery
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
description: Advanced eDiscovery упрощает управление процессом уведомления о юридических удержаниях вокруг уведомления хранителей в ходе юридических расследований.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551249"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="905e2-103">Работа с коммуникациями в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="905e2-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="905e2-104">Advanced eDiscovery позволяет юридическим отделам упрощать процессы отслеживания и распространения уведомлений о удержании.</span><span class="sxs-lookup"><span data-stu-id="905e2-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="905e2-105">Средство связи хранителя позволяет юридическим отделам управлять и автоматизировать весь процесс удержания юридических данных, начиная от начальных уведомлений и напоминаний и до эскалаций в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="905e2-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="905e2-106">Что такое юридическое уведомление о удержании?</span><span class="sxs-lookup"><span data-stu-id="905e2-106">What is a legal hold notification?</span></span>

<span data-ttu-id="905e2-107">Юридическое удержание (также известное как судебное удержание) — это уведомление, отправленное из юридического отдела организации сотрудникам, штатным сотрудникам или хранителям данных, которые могут иметь отношение к судебному расследованию.</span><span class="sxs-lookup"><span data-stu-id="905e2-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="905e2-108">Эти уведомления предписывают хранителям сохранять информацию, хранящемся в электронном виде, а также любые материалы, которые могут иметь отношение к активному или надвигаемому юридическому вопросу.</span><span class="sxs-lookup"><span data-stu-id="905e2-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="905e2-109">Юридические группы должны знать, что каждый хранитель получил, прочитал, понял и согласился выполнить указанную инструкцию.</span><span class="sxs-lookup"><span data-stu-id="905e2-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="905e2-110">Процесс уведомления о юридическом удержании</span><span class="sxs-lookup"><span data-stu-id="905e2-110">The legal hold notification process</span></span>

<span data-ttu-id="905e2-111">Организация обязана сохранять соответствующую информацию, когда узнает о предстоящем судебном разбирательстве или расследовании нормативных действий.</span><span class="sxs-lookup"><span data-stu-id="905e2-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="905e2-112">Чтобы соответствовать требованиям, предъявляемым к сохранению расследования, организация должна незамедлительно информировать потенциальных хранителей об их обязанности по сохранению соответствующей информации.</span><span class="sxs-lookup"><span data-stu-id="905e2-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="905e2-113">С Advanced eDiscovery юридические группы могут создавать и настраивать рабочий процесс уведомления о юридических удержаниях.</span><span class="sxs-lookup"><span data-stu-id="905e2-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="905e2-114">Средство связи хранителя позволяет юридическим группам настраивать следующие уведомления и рабочий процесс:</span><span class="sxs-lookup"><span data-stu-id="905e2-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="905e2-115">**Уведомление о выдаче:** Уведомление о юридическом удержании выдано (или инициировано) уведомлением из юридического отдела хранителям, которые могут иметь соответствующую информацию по данному делу.</span><span class="sxs-lookup"><span data-stu-id="905e2-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="905e2-116">Это уведомление предписывает хранителям сохранять любые сведения, которые могут потребоваться для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="905e2-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="905e2-117">**Уведомление о повторной выдаче:** В случае может потребоваться, чтобы хранители сохранили дополнительный контент (или меньше контента), чем запрашивалось ранее.</span><span class="sxs-lookup"><span data-stu-id="905e2-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="905e2-118">В этом сценарии можно обновить существующее уведомление о удержании и повторно одать его хранителям.</span><span class="sxs-lookup"><span data-stu-id="905e2-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="905e2-119">**Уведомление об освобождении:** Как только вопрос будет решен и хранитель больше не будет подвергаться требованию сохранения, хранитель может быть освобожден из дела.</span><span class="sxs-lookup"><span data-stu-id="905e2-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="905e2-120">Кроме того, вы можете уведомить хранителя о том, что он больше не требуется для сохранения контента, и предоставить инструкции по возобновлению их нормальной работы с учетом их данных.</span><span class="sxs-lookup"><span data-stu-id="905e2-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="905e2-121">**Напоминания и эскалации:** В некоторых случаях простое уведомление недостаточно для удовлетворения требований к юридическим открытиям.</span><span class="sxs-lookup"><span data-stu-id="905e2-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="905e2-122">С каждым уведомлением юридические группы могут запланировать набор процессов напоминания и эскалации, чтобы автоматически следить за хранителями, не отвечающими на уведомления.</span><span class="sxs-lookup"><span data-stu-id="905e2-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="905e2-123">**Напоминания:** После того, как уведомление о юридическом удержании было выдано или повторно выдано набору хранителей, организация может настроить напоминания, чтобы предупредить неосторожных хранителей.</span><span class="sxs-lookup"><span data-stu-id="905e2-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="905e2-124">**Эскалации:** В некоторых случаях, если хранитель остается безответным даже после набора напоминаний в течение определенного периода времени, группа юристов может настроить рабочий процесс эскалации, чтобы уведомить неопровержимые хранители и их руководителя.</span><span class="sxs-lookup"><span data-stu-id="905e2-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="905e2-125">Дополнительные сведения об управлении процессом коммуникации хранителя см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="905e2-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="905e2-126">Создание уведомления о легальном удержании</span><span class="sxs-lookup"><span data-stu-id="905e2-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="905e2-127">Использование редактора взаимодействия</span><span class="sxs-lookup"><span data-stu-id="905e2-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="905e2-128">Управление уведомлениями об удержании</span><span class="sxs-lookup"><span data-stu-id="905e2-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="905e2-129">Подтверждение уведомления об удержании</span><span class="sxs-lookup"><span data-stu-id="905e2-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)