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
description: Администратор может узнать о параметрах для настройки потока почты и маршрутов в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c988f58a04abf2322e993ae1b75106a338674acb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289655"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="1c761-103">Поток обработки почты в EOP</span><span class="sxs-lookup"><span data-stu-id="1c761-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1c761-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="1c761-104">**Applies to**</span></span>
- [<span data-ttu-id="1c761-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1c761-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1c761-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="1c761-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1c761-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c761-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="1c761-108">В организациях Microsoft 365 с почтовыми ящиками Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online все сообщения, от отправленные в организацию, проходят через EOP, прежде чем сотрудники увидят их.</span><span class="sxs-lookup"><span data-stu-id="1c761-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="1c761-109">У вас есть варианты маршрутов сообщений, которые проходят через EOP, для обработки, прежде чем они будут перена переданы в рабочие почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="1c761-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="1c761-110">Возможности для работы с сообщениями и доступа к ним</span><span class="sxs-lookup"><span data-stu-id="1c761-110">Working with messages and message access options</span></span>

<span data-ttu-id="1c761-111">EOP обеспечивает гибкость маршрутов сообщений.</span><span class="sxs-lookup"><span data-stu-id="1c761-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="1c761-112">В указанных ниже разделах описаны шаги процесса потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="1c761-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="1c761-113">[Использование блокировки на основе каталогов для отклонения сообщений, отправленных недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию блокировки на основе каталогов, которая позволяет отклонить сообщения для недопустимых получателей в периметре сети службы.</span><span class="sxs-lookup"><span data-stu-id="1c761-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="1c761-114">В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.</span><span class="sxs-lookup"><span data-stu-id="1c761-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="1c761-115">Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими.</span><span class="sxs-lookup"><span data-stu-id="1c761-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="1c761-116">Дополнительные узнать о поддоменах можно на [веб-сайте Enable mail flow for subdomains in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="1c761-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="1c761-117">[Настройка потока почты с помощью соединители](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) представляет соединители и показывает, как их можно использовать для настройки маршрутизации почты.</span><span class="sxs-lookup"><span data-stu-id="1c761-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="1c761-118">Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.</span><span class="sxs-lookup"><span data-stu-id="1c761-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="1c761-119">[В расширенной фильтрации](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) соединителях описано, как настроить соединители, если почта маршрутизирована в службу или на устройство перед EOP.</span><span class="sxs-lookup"><span data-stu-id="1c761-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="1c761-120">В автономных организациях EOP необходимо выполнить несколько действий по настройке, чтобы обеспечить правильную маршрутацию нежелательной почты в папку нежелательной почты каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1c761-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="1c761-121">Они подробно описаны в описании настройки автономных EOP для доставки нежелательной почты в папку нежелательной [почты в гибридных средах.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="1c761-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="1c761-122">Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, отредактировать политики нежелательной почты (также известные как политики фильтрации содержимого).</span><span class="sxs-lookup"><span data-stu-id="1c761-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="1c761-123">Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1c761-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="1c761-124">Проверка потока почты</span><span class="sxs-lookup"><span data-stu-id="1c761-124">Verify mail flow</span></span>

<span data-ttu-id="1c761-p106">Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="1c761-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="1c761-127">[Проверка потока почты путем проверки](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) соединителю Microsoft 365 предоставляет инструкции по проверке правильности настроенного потока почты.</span><span class="sxs-lookup"><span data-stu-id="1c761-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
