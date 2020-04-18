---
title: Совместное взаимодействие с дополнительным обнаружением электронных данных
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
description: Расширенное обнаружение электронных данных облегчает управление рабочим процессом уведомления об удержании в судебном соотношении с уведомлением о custodians в судебном расследовании.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551249"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="967d9-103">Совместное взаимодействие с дополнительным обнаружением электронных данных</span><span class="sxs-lookup"><span data-stu-id="967d9-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="967d9-104">Расширенное обнаружение электронных данных позволяет юридическим отделам упростить процессы отслеживания и распространения уведомлений о судебном удержании.</span><span class="sxs-lookup"><span data-stu-id="967d9-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="967d9-105">Средство связи хранитель позволяет юридическим подразделениям управлять и автоматизировать весь процесс судебного удержания, от первоначальных уведомлений до напоминаний и на эскалации, в одном месте.</span><span class="sxs-lookup"><span data-stu-id="967d9-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="967d9-106">Что такое уведомление о юридических удержаниях?</span><span class="sxs-lookup"><span data-stu-id="967d9-106">What is a legal hold notification?</span></span>

<span data-ttu-id="967d9-107">Уведомление о юридическом удержании (также известном как *удержание для судебного разбирательства*) — это уведомление, отправляемое из юридического отдела Организации сотрудникам, сотрудникам, взаимозависимости или custodians данных, которые могут быть важны для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="967d9-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="967d9-108">Эти уведомления указывают, что custodians сохраняют информацию, хранящуюся в электронном виде, а также любое содержимое, которое может быть релевантным для активного или ожидающего юридического лица.</span><span class="sxs-lookup"><span data-stu-id="967d9-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="967d9-109">Юридическим командам необходимо знать, что каждый хранитель получил, прочитал, понимается и принял соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="967d9-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="967d9-110">Процесс уведомления о юридических удержаниях</span><span class="sxs-lookup"><span data-stu-id="967d9-110">The legal hold notification process</span></span>

<span data-ttu-id="967d9-111">У Организации есть обязанность для сохранения релевантной информации, когда она рассказано о некотором судебном разбирательстве или законодательном расследовании.</span><span class="sxs-lookup"><span data-stu-id="967d9-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="967d9-112">Чтобы обеспечить соответствие требованиям к сохранению, Организация должна немедленно сообщить потенциально custodians о своих пошлинах, чтобы сохранить релевантную информацию.</span><span class="sxs-lookup"><span data-stu-id="967d9-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="967d9-113">Благодаря расширенному обнаружению электронных данных юридические команды могут создавать и настраивать свой рабочий процесс для уведомлений об удержаниях.</span><span class="sxs-lookup"><span data-stu-id="967d9-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="967d9-114">Средство связи хранитель позволяет юридическим группам настраивать следующие уведомления и рабочие процессы:</span><span class="sxs-lookup"><span data-stu-id="967d9-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="967d9-115">**Уведомление о выдаче:** Уведомление о юридическом удержании выдается (или инициируется) уведомлением о юридическом отделе для custodians, у которого могут быть релевантные сведения о важности.</span><span class="sxs-lookup"><span data-stu-id="967d9-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="967d9-116">Это уведомление указывает, что custodians должен сохранить любые сведения, которые могут потребоваться для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="967d9-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="967d9-117">**Уведомление о повторной выдаче:** В этом случае может потребоваться custodians для сохранения дополнительного содержимого (или меньше контента), чем ранее было запрошено.</span><span class="sxs-lookup"><span data-stu-id="967d9-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="967d9-118">В этом сценарии можно обновить существующее уведомление об удержаниях и повторно выдать его в custodians.</span><span class="sxs-lookup"><span data-stu-id="967d9-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="967d9-119">**Уведомление о выпуске:** После разрешения проблемы и хранитель не подлежит определению, хранитель может быть выпущена из этого случая.</span><span class="sxs-lookup"><span data-stu-id="967d9-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="967d9-120">Кроме того, вы можете уведомить хранитель о том, что они больше не нужны для сохранения контента, и предоставить инструкции по возобновлению нормального рабочего действия относительно их данных.</span><span class="sxs-lookup"><span data-stu-id="967d9-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="967d9-121">**Напоминания и эскалация:** В некоторых случаях просто выдача уведомления не является достаточным требованием для соблюдения юридических требований к обнаружению.</span><span class="sxs-lookup"><span data-stu-id="967d9-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="967d9-122">С каждым уведомлением юридические команды могут планировать набор напоминаний и рабочих процессов, которые автоматически поддерживайтесь с неотвечающими custodians.</span><span class="sxs-lookup"><span data-stu-id="967d9-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="967d9-123">**Напоминания:** После выдачи или повторного выдачи уведомления о юридическом удержании в набор custodians организация может настроить напоминания о необходимости оповещения о неотвечающем custodians.</span><span class="sxs-lookup"><span data-stu-id="967d9-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="967d9-124">**Эскалация:** В некоторых случаях, если хранитель не реагирует даже после набора напоминаний за определенный период времени, юридический специалист может настроить рабочий процесс эскалации, чтобы уведомить о неотвечающем custodians и их руководителе.</span><span class="sxs-lookup"><span data-stu-id="967d9-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="967d9-125">Для получения дополнительных сведений об управлении процессом связи хранитель обратитесь к следующим разделам:</span><span class="sxs-lookup"><span data-stu-id="967d9-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="967d9-126">Создание уведомления об судебном удержании</span><span class="sxs-lookup"><span data-stu-id="967d9-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="967d9-127">Использование редактора взаимодействия</span><span class="sxs-lookup"><span data-stu-id="967d9-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="967d9-128">Управление уведомлениями об удержании</span><span class="sxs-lookup"><span data-stu-id="967d9-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="967d9-129">Подтверждение уведомления об удержании</span><span class="sxs-lookup"><span data-stu-id="967d9-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)