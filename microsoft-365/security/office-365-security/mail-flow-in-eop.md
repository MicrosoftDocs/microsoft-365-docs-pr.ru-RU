---
title: Поток обработки почты в службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать о параметрах настройки потока почты и маршрутинга в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842498"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="4b0ac-103">Поток обработки почты в EOP</span><span class="sxs-lookup"><span data-stu-id="4b0ac-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4b0ac-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="4b0ac-104">**Applies to**</span></span>
- [<span data-ttu-id="4b0ac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4b0ac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4b0ac-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="4b0ac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4b0ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b0ac-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4b0ac-108">В Microsoft 365 организациях с Exchange Online почтовыми ящиками или автономными организациями Exchange Online Protection (EOP) без Exchange Online почтовых ящиков все сообщения, отправленные в организацию, передаются через EOP перед их просмотром сотрудниками.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="4b0ac-109">У вас есть варианты маршрутивка сообщений, которые передаются через EOP для обработки, прежде чем они будут переданы в почтовые ящики рабочих.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="4b0ac-110">Возможности для работы с сообщениями и доступа к ним</span><span class="sxs-lookup"><span data-stu-id="4b0ac-110">Working with messages and message access options</span></span>

<span data-ttu-id="4b0ac-111">EOP обеспечивает гибкость в маршрутных маршрутах сообщений.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="4b0ac-112">В указанных ниже разделах описаны шаги процесса потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="4b0ac-113">[Использование блокировки края на основе каталога для отклонить сообщения, отправленные недействительным получателям](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию блокировки на основе каталогов, которая позволяет отклонить сообщения для недействительных получателей в периметре сети службы.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="4b0ac-114">[Просмотр или изменение принятых доменов](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в EOP описывает управление доменами, связанными с вашей службой EOP.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-114">[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="4b0ac-115">Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="4b0ac-116">Дополнительные новости о поддоменах в списке Включить поток почты для [поддоменов](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)в Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="4b0ac-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="4b0ac-117">[Настройка потока почты с помощью соединители](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) вводит соединители и показывает, как их можно использовать для настройки маршрутизации почты.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="4b0ac-118">Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="4b0ac-119">[Расширенная фильтрация соединители описывает](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) настройку соединители, если ваша почта передается в службу или устройство перед EOP.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="4b0ac-120">В гибридных средах, в которых EOP защищает локальные почтовые ящики Exchange, требуется настроить правила потока обработки почты (также называемые правилами транспорта) в локальной среде Exchange для преобразования решения фильтра нежелательной почты EOP, чтобы правило нежелательной почты могло перемещать сообщение в папку "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="4b0ac-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="4b0ac-121">Дополнительные сведения см. в статье [Настройка EOP для доставки спама в папку нежелательной почты в гибридных средах](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span><span class="sxs-lookup"><span data-stu-id="4b0ac-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="4b0ac-122">Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, редактировать политики по борьбе со спамом (также известные как политики фильтра контента).</span><span class="sxs-lookup"><span data-stu-id="4b0ac-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="4b0ac-123">Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4b0ac-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="4b0ac-124">Проверка потока почты</span><span class="sxs-lookup"><span data-stu-id="4b0ac-124">Verify mail flow</span></span>

<span data-ttu-id="4b0ac-p106">Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](/exchange/standalone-eop/set-up-your-eop-service).</span><span class="sxs-lookup"><span data-stu-id="4b0ac-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="4b0ac-127">[Проверка потока почты](/exchange/mail-flow-best-practices/test-mail-flow) путем проверки Microsoft 365 соединителю предоставляет инструкции по проверке правильной настройка потока почты.</span><span class="sxs-lookup"><span data-stu-id="4b0ac-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
