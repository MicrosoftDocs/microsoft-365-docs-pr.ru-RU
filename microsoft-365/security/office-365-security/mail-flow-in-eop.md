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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Администратор изучите параметры настройки потока обработки почты и маршрутизации в Exchange Online Protection (EOP).
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827729"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="e1c32-103">Поток обработки почты в службе EOP</span><span class="sxs-lookup"><span data-stu-id="e1c32-103">Mail flow in EOP</span></span>

<span data-ttu-id="e1c32-104">В организациях Microsoft 365 с почтовыми ящиками Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) все сообщения, отправляемые в организацию, проходят через EOP до того, как ваши звонят ваши клиенты.</span><span class="sxs-lookup"><span data-stu-id="e1c32-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="e1c32-105">Перенаправлять сообщения, которые проходят через EOP, можно перед их маршрутизацией в папки "Входящие" ваших рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="e1c32-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="e1c32-106">Возможности для работы с сообщениями и доступа к ним</span><span class="sxs-lookup"><span data-stu-id="e1c32-106">Working with messages and message access options</span></span>

<span data-ttu-id="e1c32-107">Служба EOP обеспечивает гибкость в маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="e1c32-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="e1c32-108">В указанных ниже разделах описаны шаги процесса потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="e1c32-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="e1c32-109">[Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправленных недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описание функции пограничной блокировки на основе каталогов, которая позволяет отклонять сообщения для недопустимых получателей в периметре сервисной сети.</span><span class="sxs-lookup"><span data-stu-id="e1c32-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="e1c32-110">В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.</span><span class="sxs-lookup"><span data-stu-id="e1c32-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="e1c32-111">Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими.</span><span class="sxs-lookup"><span data-stu-id="e1c32-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="e1c32-112">Дополнительные сведения о поддоменах см. в [разделе "Включение потока обработки почты для поддоменов в Exchange Online".](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="e1c32-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="e1c32-113">[Настройка потока обработки почты с помощью](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) соединителей ознакомления и их использование при настройке маршрутизации почты.</span><span class="sxs-lookup"><span data-stu-id="e1c32-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="e1c32-114">Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.</span><span class="sxs-lookup"><span data-stu-id="e1c32-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="e1c32-115">[Улучшенная фильтрация для соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) описывает, как настроить соединители, если почта направляется в службу или на устройство перед EOP.</span><span class="sxs-lookup"><span data-stu-id="e1c32-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="e1c32-116">Чтобы нежелательная почта правильно маршрутизировалась в папки нежелательной почты каждого пользователя, необходимо выполнить несколько действий по настройке.</span><span class="sxs-lookup"><span data-stu-id="e1c32-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="e1c32-117">Они подробно рассмотрены [в разделе "Настройка автономной службы EOP для доставки спама в папку нежелательной почты в гибридных средах".](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="e1c32-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="e1c32-118">Если вы не хотите перемещать сообщения в папку "Нежелательная почта" каждого пользователя, можно выбрать другое действие с помощью политик защиты от нежелательной почты (также называемых политиками фильтрации содержимого).</span><span class="sxs-lookup"><span data-stu-id="e1c32-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="e1c32-119">Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e1c32-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="e1c32-120">Проверка потока почты</span><span class="sxs-lookup"><span data-stu-id="e1c32-120">Verify mail flow</span></span>

<span data-ttu-id="e1c32-p106">Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="e1c32-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="e1c32-123">[Протестируйте поток обработки почты, проверив соединители Microsoft 365,](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) следуя инструкциям по проверке правильности настройки потока обработки почты.</span><span class="sxs-lookup"><span data-stu-id="e1c32-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
