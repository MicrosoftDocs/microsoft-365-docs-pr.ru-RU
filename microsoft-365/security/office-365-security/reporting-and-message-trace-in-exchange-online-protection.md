---
title: Отчеты и трассировка сообщений
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: В этой статье вы узнаете о отчетах и средствах устранения неполадок, доступных администраторам Microsoft Exchange Online защиты (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5e5493925a17725bfb9d6698b3f94050960ccc7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205720"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="10f22-103">Отчеты и трассировка сообщений в EOP</span><span class="sxs-lookup"><span data-stu-id="10f22-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="10f22-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="10f22-104">**Applies to**</span></span>
- [<span data-ttu-id="10f22-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="10f22-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="10f22-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="10f22-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="10f22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10f22-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="10f22-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online EOP предлагает множество различных отчетов, которые помогут определить общее состояние и состояние вашей организации.</span><span class="sxs-lookup"><span data-stu-id="10f22-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="10f22-109">Существуют также средства, позволяющие устранять неполадки с определенными событиями (например, если сообщение не приходит указанным получателям), а также отчеты аудита для целей соответствия требованиями.</span><span class="sxs-lookup"><span data-stu-id="10f22-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="10f22-110">Отчеты об использовании</span><span class="sxs-lookup"><span data-stu-id="10f22-110">Usage reports</span></span>

<span data-ttu-id="10f22-111">**Действия групп Microsoft 365.** Просмотр сведений о количестве созданных и используемых групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10f22-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="10f22-112">**Действия электронной почты:** просмотр сведений о количестве сообщений, отправленных, полученных и читаемых во всей организации, а также определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="10f22-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="10f22-113">**Использование приложения электронной почты.** Просмотр сведений об используемых приложениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="10f22-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="10f22-114">Это включает общее количество подключений для каждого приложения и версии подключаемого Outlook.</span><span class="sxs-lookup"><span data-stu-id="10f22-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="10f22-115">**Использование почтовых ящиков.** Просмотр сведений об используемом хранилище, потреблении квот, подсчете элементов и последнем действии (отправка или чтение) для почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="10f22-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="10f22-116">Дополнительные сведения можно найти в следующих материалах:</span><span class="sxs-lookup"><span data-stu-id="10f22-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="10f22-117">Отчеты Microsoft 365 в центре администрирования — группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10f22-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="10f22-118">Отчеты Microsoft 365 в центре администрирования — действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="10f22-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="10f22-119">Отчеты Microsoft 365 в центре администрирования — использование приложений электронной почты</span><span class="sxs-lookup"><span data-stu-id="10f22-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="10f22-120">Отчеты Microsoft 365 в центре администрирования — использование почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="10f22-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="10f22-121">Отчеты & безопасности в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10f22-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="10f22-122">Эти расширенные отчеты предоставляют возможность интерактивной отчетности для администраторов EOP, которая включает сводную информацию и возможность сверлить дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="10f22-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="10f22-123">**Defender for Office 365**: Просмотр сведений о безопасных ссылках и безопасных вложениях, которые являются частью Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="10f22-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="10f22-124">**EOP**. Просмотр сведений об обнаружении вредоносных программ, подмене почты, обнаружения нежелательной почты и потоках почты в организацию и из нее.</span><span class="sxs-lookup"><span data-stu-id="10f22-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="10f22-125">Просмотр отчетов для Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="10f22-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="10f22-126">Настраиваемые отчеты с помощью Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="10f22-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="10f22-127">Программным образом создайте отчеты, доступные в центре администрирования с помощью Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="10f22-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="10f22-128">Дополнительные сведения см. в [обзоре отчетов об](/graph/overview) использовании Microsoft Graph и [Working with Office 365 в Microsoft Graph.](/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="10f22-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="10f22-129">Трассировка сообщений</span><span class="sxs-lookup"><span data-stu-id="10f22-129">Message trace</span></span>

<span data-ttu-id="10f22-130">Отслеживает сообщения электронной почты, проходящие через EOP.</span><span class="sxs-lookup"><span data-stu-id="10f22-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="10f22-131">Можно определить, было ли сообщение получено, отклонено, задержано или доставлено службой.</span><span class="sxs-lookup"><span data-stu-id="10f22-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="10f22-132">В нем также показано, какие действия были приняты в сообщении до его окончательного состояния.</span><span class="sxs-lookup"><span data-stu-id="10f22-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="10f22-133">Эти сведения можно использовать для эффективного ответа на вопросы пользователя, устранения неполадок с потоком почты, проверки изменений политики и устранения необходимости обращаться за помощью в техническую поддержку.</span><span class="sxs-lookup"><span data-stu-id="10f22-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="10f22-134">См. [трассировка сообщения в центре & безопасности.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="10f22-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="10f22-135">Ведение журнала аудита</span><span class="sxs-lookup"><span data-stu-id="10f22-135">Audit logging</span></span>

<span data-ttu-id="10f22-136">Отслеживает определенные изменения, выполненные администраторами в организации.</span><span class="sxs-lookup"><span data-stu-id="10f22-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="10f22-137">Эти отчеты позволяют устранять неполадки конфигурации и определять причины проблем безопасности или соблюдения требований.</span><span class="sxs-lookup"><span data-stu-id="10f22-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="10f22-138">См. [отчеты о аудите в EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="10f22-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="10f22-139">Отчеты и трассировка сообщений: доступность данных и задержка</span><span class="sxs-lookup"><span data-stu-id="10f22-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="10f22-140">В таблице ниже описано, когда и в течение какого времени доступны данные отчетов и трассировки сообщений EOP.</span><span class="sxs-lookup"><span data-stu-id="10f22-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="10f22-141">Тип отчета</span><span class="sxs-lookup"><span data-stu-id="10f22-141">Report type</span></span>|<span data-ttu-id="10f22-142">Доступные данные (период просмотра)</span><span class="sxs-lookup"><span data-stu-id="10f22-142">Data available for (look back period)</span></span>|<span data-ttu-id="10f22-143">Задержка</span><span class="sxs-lookup"><span data-stu-id="10f22-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="10f22-144">Сводные отчеты о защите почты</span><span class="sxs-lookup"><span data-stu-id="10f22-144">Mail protection summary reports</span></span>|<span data-ttu-id="10f22-145">90 дней</span><span class="sxs-lookup"><span data-stu-id="10f22-145">90 days</span></span>|<span data-ttu-id="10f22-p106">Агрегирование данных сообщений в основном выполняется в течение 24-48 часов. Постепенное внесение незначительных изменений при агрегировании может занять до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="10f22-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="10f22-148">Отчеты о защите почты</span><span class="sxs-lookup"><span data-stu-id="10f22-148">Mail protection detail reports</span></span>|<span data-ttu-id="10f22-149">90 дней</span><span class="sxs-lookup"><span data-stu-id="10f22-149">90 days</span></span>|<span data-ttu-id="10f22-p107">Более подробные данные с давностью не более 7 дней появятся в течение 24 часов, но могут быть неполными в течение 48 часов. Постепенное внесение незначительных изменений может занять до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="10f22-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="10f22-152">Для отображения подробных отчетов о сообщениях с давностью более 7 дней может понадобиться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="10f22-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="10f22-153">Данные трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="10f22-153">Message trace data</span></span>|<span data-ttu-id="10f22-154">90 дней</span><span class="sxs-lookup"><span data-stu-id="10f22-154">90 days</span></span>|<span data-ttu-id="10f22-155">Трассировка сообщений с давностью менее 7 дней может занять от 5 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="10f22-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="10f22-156">Трассировка сообщений с давностью более 7 дней может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="10f22-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="10f22-157">Доступность и задержка данных являются одинаковыми независимо от того, запрашиваются ли они в центре администрирования или удаленной PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10f22-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>