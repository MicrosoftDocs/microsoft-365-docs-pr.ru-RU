---
title: Поток обработки почты в службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: В этой статье Exchange Online Protection (EOP) пользователи могут узнать о настройке настраиваемой маршрутизации почты, которая может соответствовать бизнес-требованиям.
ms.openlocfilehash: cdc919c628f2254ffc971678f7887c37786d2528
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034236"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="0c3fc-103">Поток обработки почты в службе EOP</span><span class="sxs-lookup"><span data-stu-id="0c3fc-103">Mail flow in EOP</span></span>

<span data-ttu-id="0c3fc-p101">Поскольку вы являетесь пользователем Exchange Online Protection (EOP), все сообщения, отправляемые в организацию, проходят через службу EOP перед доставкой сотрудникам. Если все ваши почтовые ящики находятся в облаке с Exchange Online или хранятся локально (т. е. используется изолированный сценарий), возможно, для дальнейшего использования текущей инфраструктуры у вас есть возможности направлять сообщения, проходящие через службу EOP, для обработки, прежде чем они будут доставлены в папки "Входящие" ваших сотрудников.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-p101">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>

<span data-ttu-id="0c3fc-p102">Возможно, следует настроить пользовательскую маршрутизацию почты, чтобы привести обмен сообщениями в соответствие с вашими бизнес-требованиями. Например, вы можете задать прохождение всей исходящей почты через устройство фильтрации политики.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-p102">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="0c3fc-108">Возможности для работы с сообщениями и доступа к ним</span><span class="sxs-lookup"><span data-stu-id="0c3fc-108">Working with messages and message access options</span></span>

<span data-ttu-id="0c3fc-p103">Служба EOP позволяет гибко маршрутизировать сообщения. В указанных ниже разделах описаны шаги процесса потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-p103">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="0c3fc-111">[Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправляемых недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию пограничной блокировки на основе каталогов, которая позволяет отклонять сообщения для недопустимых получателей в сети периметра службы.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-111">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="0c3fc-112">В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-112">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="0c3fc-113">Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-113">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="0c3fc-114">Дополнительные сведения о поддоменах [позволяют включить почтовые потоки для поддоменов в Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="0c3fc-114">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="0c3fc-p105">В разделе [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) описываются соединители и их использование для настройки маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-p105">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="0c3fc-117">Чтобы убедиться, что нежелательная почта правильно направляется в папку нежелательной почты каждого пользователя, необходимо выполнить несколько действий по настройке.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-117">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps.</span></span> <span data-ttu-id="0c3fc-118">Они подробно описаны в разделе [Настройка автономных EOP для доставки спама в папку нежелательной почты в гибридных средах](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="0c3fc-118">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="0c3fc-119">Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, отредактировав политики фильтрации содержимого в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-119">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="0c3fc-120">Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0c3fc-120">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="0c3fc-121">Проверка потока почты</span><span class="sxs-lookup"><span data-stu-id="0c3fc-121">Verify mail flow</span></span>

<span data-ttu-id="0c3fc-p107">Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="0c3fc-p107">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="0c3fc-124">[Проверьте процесс обработки почты, проверив соединители Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) . инструкции по проверке правильности настройки почтового процесса.</span><span class="sxs-lookup"><span data-stu-id="0c3fc-124">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
