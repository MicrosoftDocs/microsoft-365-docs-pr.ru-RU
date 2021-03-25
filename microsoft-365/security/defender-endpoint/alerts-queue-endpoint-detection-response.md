---
title: Очередь оповещений в Центре безопасности Защитника Майкрософт
ms.reviewer: ''
description: Просмотр и управление оповещениями, которые всплыли в Центре безопасности Защитника Майкрософт
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075438"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="7e689-103">Очередь оповещений в Центре безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7e689-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7e689-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7e689-104">**Applies to:**</span></span>
- [<span data-ttu-id="7e689-105">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7e689-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="7e689-106">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7e689-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7e689-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7e689-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7e689-108">Узнайте, как можно просматривать и управлять очередью, чтобы эффективно исследовать угрозы, замеченные на устройствах, файлах или учетных записях пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e689-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7e689-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7e689-109">In this section</span></span>
<span data-ttu-id="7e689-110">Статья</span><span class="sxs-lookup"><span data-stu-id="7e689-110">Topic</span></span> | <span data-ttu-id="7e689-111">Описание</span><span class="sxs-lookup"><span data-stu-id="7e689-111">Description</span></span> 
:---|:---
[<span data-ttu-id="7e689-112">Просмотр и организация очереди оповещений</span><span class="sxs-lookup"><span data-stu-id="7e689-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="7e689-113">Показывает список оповещений, помеченных в сети.</span><span class="sxs-lookup"><span data-stu-id="7e689-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="7e689-114">Управление оповещениями</span><span class="sxs-lookup"><span data-stu-id="7e689-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="7e689-115">Узнайте, как управлять оповещениями, такими как изменение его состояния, назначить его участнику операций безопасности и посмотреть историю оповещения.</span><span class="sxs-lookup"><span data-stu-id="7e689-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="7e689-116">Исследование оповещений</span><span class="sxs-lookup"><span data-stu-id="7e689-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="7e689-117">Изучите оповещения, влияющие на вашу сеть, поймите, что они означают, и как их устранить.</span><span class="sxs-lookup"><span data-stu-id="7e689-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="7e689-118">Исследование файлов</span><span class="sxs-lookup"><span data-stu-id="7e689-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="7e689-119">Изучите сведения о файле, связанном с определенным предупреждением, поведением или событием.</span><span class="sxs-lookup"><span data-stu-id="7e689-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="7e689-120">Исследование устройств</span><span class="sxs-lookup"><span data-stu-id="7e689-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="7e689-121">Изучите сведения о устройстве, связанном с определенным предупреждением, поведением или событием.</span><span class="sxs-lookup"><span data-stu-id="7e689-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="7e689-122">Исследование IP-адреса</span><span class="sxs-lookup"><span data-stu-id="7e689-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="7e689-123">Изучите возможную связь между устройствами в сети и внешними IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="7e689-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="7e689-124">Исследование домена</span><span class="sxs-lookup"><span data-stu-id="7e689-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="7e689-125">Изучите домен, чтобы узнать, связывались ли устройства и серверы в сети с известным вредоносным доменом.</span><span class="sxs-lookup"><span data-stu-id="7e689-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="7e689-126">Исследование учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="7e689-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="7e689-127">Определите учетные записи пользователей с помощью наиболее активных оповещений и изучите случаи потенциального взлома учетных данных.</span><span class="sxs-lookup"><span data-stu-id="7e689-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  

