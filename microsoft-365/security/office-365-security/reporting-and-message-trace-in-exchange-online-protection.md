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
description: В этой статье вы узнаете об отчетах и средствах устранения неполадок, доступных администраторам Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 149f7fa36a717a92d3cda5f6f3f82651f0144d73
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827633"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="3ca87-103">Отчеты и трассировка сообщений в службе EOP</span><span class="sxs-lookup"><span data-stu-id="3ca87-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="3ca87-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) без почтовых ящиков Exchange Online в службе EOP доступно множество различных отчетов, с помощью которых вы сможете определить общее состояние и работоспособность вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3ca87-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="3ca87-105">Существуют также средства, позволяющие устранять неполадки с определенными событиями (например, если сообщение не приходит указанным получателям), а также отчеты аудита для целей соответствия требованиями.</span><span class="sxs-lookup"><span data-stu-id="3ca87-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="3ca87-106">Отчеты об использовании</span><span class="sxs-lookup"><span data-stu-id="3ca87-106">Usage reports</span></span>

<span data-ttu-id="3ca87-107">**Действия в группах Microsoft 365:** просмотр сведений о количестве созданных и используемых групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ca87-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="3ca87-108">**Действия с электронной**почтой: просмотр сведений о количестве отправленных, полученных и прочитанных сообщений во всей организации, а также определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3ca87-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="3ca87-109">**Использование почтовых приложений:** просмотр сведений об используемых почтовых приложениях.</span><span class="sxs-lookup"><span data-stu-id="3ca87-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="3ca87-110">Сюда относится общее число подключений для каждого приложения и версии Outlook, которые подключаются.</span><span class="sxs-lookup"><span data-stu-id="3ca87-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="3ca87-111">**Использование почтовых ящиков:** просмотр сведений об используемом хранилище, потребении квоты, числе элементов и последних действиях (отправке и чтение) для почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="3ca87-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="3ca87-112">Дополнительные сведения можно найти в следующих материалах:</span><span class="sxs-lookup"><span data-stu-id="3ca87-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="3ca87-113">Отчеты по Microsoft 365 в Центре администрирования группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ca87-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="3ca87-114">Отчеты в Центре администрирования Microsoft 365 действия электронной почты</span><span class="sxs-lookup"><span data-stu-id="3ca87-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="3ca87-115">Отчеты Microsoft 365 в Центре администрирования использование почтовых приложений</span><span class="sxs-lookup"><span data-stu-id="3ca87-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="3ca87-116">Отчеты в Центре администрирования Microsoft 365 использование почтового ящика</span><span class="sxs-lookup"><span data-stu-id="3ca87-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3ca87-117">Отчеты & соответствия требованиям безопасности в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ca87-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3ca87-118">Эти улучшенные отчеты предоставляют интерактивные возможности для создания отчетов для администраторов EOP, включая сводные сведения и возможность детализировать для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="3ca87-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="3ca87-119">**Расширенная защита от угроз (ATP):** просмотр сведений о функции "безопасные ссылки" и "Безопасных вложениях", которые являются частью ATP.</span><span class="sxs-lookup"><span data-stu-id="3ca87-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="3ca87-120">**EOP:** просмотр сведений об обнаруженных вредоносных программах, поддельной почте, обнаружении нежелательной почты и потоке обработки почты в организацию и из нее.</span><span class="sxs-lookup"><span data-stu-id="3ca87-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="3ca87-121">Просмотр отчетов для Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3ca87-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="3ca87-122">Пользовательские отчеты, используя Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3ca87-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="3ca87-123">Создайте отчеты, доступные в Центре администрирования с помощью Microsoft Graph программным способом.</span><span class="sxs-lookup"><span data-stu-id="3ca87-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="3ca87-124">Дополнительные сведения см. в [статье "Обзор Microsoft Graph](https://docs.microsoft.com/graph/overview) и работа с [отчетами об использовании Office 365" в Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="3ca87-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="3ca87-125">Трассировка сообщений</span><span class="sxs-lookup"><span data-stu-id="3ca87-125">Message trace</span></span>

<span data-ttu-id="3ca87-126">Отслеживает сообщения электронной почты, проходящие через EOP.</span><span class="sxs-lookup"><span data-stu-id="3ca87-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="3ca87-127">Можно определить, было ли сообщение получено, отклонено, задержано или доставлено службой.</span><span class="sxs-lookup"><span data-stu-id="3ca87-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="3ca87-128">В нем также показаны действия, выполненные над сообщением, до того как оно достигло окончательного состояния.</span><span class="sxs-lookup"><span data-stu-id="3ca87-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="3ca87-129">Вы можете использовать эти сведения для эффективного ответа на вопросы пользователей, устранять неполадки потока сообщений, проверять изменения политик и снижать необходимость обращения за помощью в службу технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="3ca87-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="3ca87-130">См. [трассировку сообщений в Центре безопасности & соответствия требованиям.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="3ca87-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="3ca87-131">Ведение журнала аудита</span><span class="sxs-lookup"><span data-stu-id="3ca87-131">Audit logging</span></span>

<span data-ttu-id="3ca87-132">Отслеживает определенные изменения, выполненные администраторами в организации.</span><span class="sxs-lookup"><span data-stu-id="3ca87-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="3ca87-133">Эти отчеты позволяют устранять неполадки конфигурации и определять причины проблем безопасности или соблюдения требований.</span><span class="sxs-lookup"><span data-stu-id="3ca87-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="3ca87-134">См. [отчеты аудита в EOP.](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="3ca87-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="3ca87-135">Отчеты и трассировка сообщений: доступность данных и задержка</span><span class="sxs-lookup"><span data-stu-id="3ca87-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="3ca87-136">В таблице ниже описано, когда и в течение какого времени доступны данные отчетов и трассировки сообщений EOP.</span><span class="sxs-lookup"><span data-stu-id="3ca87-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="3ca87-137">Тип отчета</span><span class="sxs-lookup"><span data-stu-id="3ca87-137">Report type</span></span>|<span data-ttu-id="3ca87-138">Доступные данные (период просмотра)</span><span class="sxs-lookup"><span data-stu-id="3ca87-138">Data available for (look back period)</span></span>|<span data-ttu-id="3ca87-139">Задержка</span><span class="sxs-lookup"><span data-stu-id="3ca87-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="3ca87-140">Сводные отчеты о защите почты</span><span class="sxs-lookup"><span data-stu-id="3ca87-140">Mail protection summary reports</span></span>|<span data-ttu-id="3ca87-141">90 дней</span><span class="sxs-lookup"><span data-stu-id="3ca87-141">90 days</span></span>|<span data-ttu-id="3ca87-p106">Агрегирование данных сообщений в основном выполняется в течение 24-48 часов. Постепенное внесение незначительных изменений при агрегировании может занять до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca87-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="3ca87-144">Подробные отчеты о защите почты</span><span class="sxs-lookup"><span data-stu-id="3ca87-144">Mail protection detail reports</span></span>|<span data-ttu-id="3ca87-145">90 дней</span><span class="sxs-lookup"><span data-stu-id="3ca87-145">90 days</span></span>|<span data-ttu-id="3ca87-p107">Более подробные данные с давностью не более 7 дней появятся в течение 24 часов, но могут быть неполными в течение 48 часов. Постепенное внесение незначительных изменений может занять до 5 дней.</span><span class="sxs-lookup"><span data-stu-id="3ca87-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="3ca87-148">Для отображения подробных отчетов о сообщениях с давностью более 7 дней может понадобиться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="3ca87-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="3ca87-149">Данные трассировки сообщений</span><span class="sxs-lookup"><span data-stu-id="3ca87-149">Message trace data</span></span>|<span data-ttu-id="3ca87-150">90 дней</span><span class="sxs-lookup"><span data-stu-id="3ca87-150">90 days</span></span>|<span data-ttu-id="3ca87-151">Трассировка сообщений с давностью менее 7 дней может занять от 5 до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="3ca87-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="3ca87-152">Трассировка сообщений с давностью более 7 дней может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="3ca87-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="3ca87-153">Доступность и задержка данных аналогична запрошенным в Центре администрирования или в удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ca87-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
