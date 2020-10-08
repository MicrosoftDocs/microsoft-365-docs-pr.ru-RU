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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: В этой статье рассказывается о отчетах и средствах устранения неполадок, доступных администраторам Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 86f4e18430324ed95f036f93746d826225ec3b2f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196403"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="bbd42-103">Отчеты и трассировка сообщений в EOP</span><span class="sxs-lookup"><span data-stu-id="bbd42-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bbd42-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или Exchange Online Protection (EOP) без почтовых ящиков Exchange Online, EOP предлагает множество различных отчетов, которые могут помочь определить общее состояние и работоспособность Организации.</span><span class="sxs-lookup"><span data-stu-id="bbd42-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="bbd42-105">Существуют также средства, позволяющие устранять неполадки с определенными событиями (например, если сообщение не приходит указанным получателям), а также отчеты аудита для целей соответствия требованиями.</span><span class="sxs-lookup"><span data-stu-id="bbd42-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="bbd42-106">Отчеты об использовании</span><span class="sxs-lookup"><span data-stu-id="bbd42-106">Usage reports</span></span>

<span data-ttu-id="bbd42-107">**Действия в группах microsoft 365**: Просмотр сведений о количестве созданных и используемых групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbd42-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="bbd42-108">**Действия с электронной почтой**: Просмотр сведений о количестве отправленных, полученных и прочитанных сообщений в Организации и определенных пользователях.</span><span class="sxs-lookup"><span data-stu-id="bbd42-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="bbd42-109">**Использование почтовых**приложений: Просмотр сведений о почтовых приложениях, которые используются.</span><span class="sxs-lookup"><span data-stu-id="bbd42-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="bbd42-110">Сюда входят общее число подключений для каждого приложения и версии Outlook, которые подключаются.</span><span class="sxs-lookup"><span data-stu-id="bbd42-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="bbd42-111">**Использование почтового ящика**: Просмотр сведений об используемых хранилищах, потреблении квот, количестве элементов и последних действиях для почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="bbd42-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="bbd42-112">Дополнительные сведения можно найти в следующих материалах:</span><span class="sxs-lookup"><span data-stu-id="bbd42-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="bbd42-113">Отчеты Microsoft 365 в центре администрирования — группы Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="bbd42-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="bbd42-114">Отчеты Microsoft 365 в центре администрирования — действие электронной почты</span><span class="sxs-lookup"><span data-stu-id="bbd42-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="bbd42-115">Отчеты Microsoft 365 в центре администрирования — использование почтовых приложений</span><span class="sxs-lookup"><span data-stu-id="bbd42-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="bbd42-116">Отчеты Microsoft 365 в центре администрирования — использование почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="bbd42-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="bbd42-117">Отчеты о соответствии & безопасности в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bbd42-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="bbd42-118">Эти расширенные отчеты предоставляют Интерактивные отчеты для администраторов EOP, включающие сводную информацию и возможность детализации для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="bbd42-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="bbd42-119">**Advanced Threat protection (ATP)**: Просмотр сведений о безопасных ссылках и безопасных вложениях, которые входят в состав ATP.</span><span class="sxs-lookup"><span data-stu-id="bbd42-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="bbd42-120">**EOP**: Просмотр сведений об обнаружении вредоносных программ, поддельной почте, обнаружении нежелательной почты и потоки обработки почты в Организации и из нее.</span><span class="sxs-lookup"><span data-stu-id="bbd42-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="bbd42-121">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="bbd42-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="bbd42-122">Настраиваемые отчеты с помощью Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="bbd42-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="bbd42-123">Программно создайте отчеты, доступные в центре администрирования, с помощью Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="bbd42-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="bbd42-124">Дополнительные сведения см. в [статье Обзор Microsoft Graph](https://docs.microsoft.com/graph/overview) и [Работа с отчетами об использовании Office 365 в Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="bbd42-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="bbd42-125">Трассировка сообщений</span><span class="sxs-lookup"><span data-stu-id="bbd42-125">Message trace</span></span>

<span data-ttu-id="bbd42-126">Отслеживает сообщения электронной почты, проходящие через EOP.</span><span class="sxs-lookup"><span data-stu-id="bbd42-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="bbd42-127">Можно определить, было ли сообщение получено, отклонено, задержано или доставлено службой.</span><span class="sxs-lookup"><span data-stu-id="bbd42-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="bbd42-128">Кроме того, здесь показано, какие действия были выполнены над сообщением до достижения его последнего состояния.</span><span class="sxs-lookup"><span data-stu-id="bbd42-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="bbd42-129">Вы можете использовать эти сведения для эффективного ответа на вопросы пользователя, устранения проблем с потоками обработки почты, проверки изменений политик и устранения необходимости обращения в службу технической поддержки за помощью.</span><span class="sxs-lookup"><span data-stu-id="bbd42-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="bbd42-130">Просмотрите [трассировку сообщений в центре безопасности & соответствия требованиям](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="bbd42-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="bbd42-131">Ведение журнала аудита</span><span class="sxs-lookup"><span data-stu-id="bbd42-131">Audit logging</span></span>

<span data-ttu-id="bbd42-132">Отслеживает определенные изменения, выполненные администраторами в организации.</span><span class="sxs-lookup"><span data-stu-id="bbd42-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="bbd42-133">Эти отчеты позволяют устранять неполадки конфигурации и определять причины проблем безопасности или соблюдения требований.</span><span class="sxs-lookup"><span data-stu-id="bbd42-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="bbd42-134">[В разделе Отчеты об аудите в EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="bbd42-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="bbd42-135">Отчеты и трассировка сообщений: доступность данных и задержка</span><span class="sxs-lookup"><span data-stu-id="bbd42-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="bbd42-136">В таблице ниже описано, когда и в течение какого времени доступны данные отчетов и трассировки сообщений EOP.</span><span class="sxs-lookup"><span data-stu-id="bbd42-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="bbd42-137">Тип отчета</span><span class="sxs-lookup"><span data-stu-id="bbd42-137">Report type</span></span>|<span data-ttu-id="bbd42-138">Доступные данные (период просмотра)</span><span class="sxs-lookup"><span data-stu-id="bbd42-138">Data available for (look back period)</span></span>|<span data-ttu-id="bbd42-139">Задержка</span><span class="sxs-lookup"><span data-stu-id="bbd42-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="bbd42-140">Сводные отчеты о защите почты</span><span class="sxs-lookup"><span data-stu-id="bbd42-140">Mail protection summary reports</span></span>|<span data-ttu-id="bbd42-141">90 дней</span><span class="sxs-lookup"><span data-stu-id="bbd42-141">90 days</span></span>|<span data-ttu-id="bbd42-p106">Агрегирование данных сообщений в основном выполняется в течение 24-48 часов. Постепенное внесение незначительных изменений при агрегировании может занять до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="bbd42-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="bbd42-144">Подробные отчеты о защите почты</span><span class="sxs-lookup"><span data-stu-id="bbd42-144">Mail protection detail reports</span></span>|<span data-ttu-id="bbd42-145">90 дней</span><span class="sxs-lookup"><span data-stu-id="bbd42-145">90 days</span></span>|<span data-ttu-id="bbd42-p107">Более подробные данные с давностью не более 7 дней появятся в течение 24 часов, но могут быть неполными в течение 48 часов. Постепенное внесение незначительных изменений может занять до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="bbd42-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="bbd42-148">Для отображения подробных отчетов о сообщениях с давностью более 7 дней может понадобиться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="bbd42-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="bbd42-149">Данные трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="bbd42-149">Message trace data</span></span>|<span data-ttu-id="bbd42-150">90 дней</span><span class="sxs-lookup"><span data-stu-id="bbd42-150">90 days</span></span>|<span data-ttu-id="bbd42-151">Трассировка сообщений с давностью менее 7 дней может занять от 5 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="bbd42-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="bbd42-152">Трассировка сообщений с давностью более 7 дней может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="bbd42-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="bbd42-153">Доступность данных и задержка это то же, что и по запросу через центр администрирования или удаленную оболочку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbd42-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
