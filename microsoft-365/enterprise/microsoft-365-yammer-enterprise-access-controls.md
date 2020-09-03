---
title: Элементы управления доступом к Microsoft 365 Yammer корпоративный
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: В этой статье представлен краткий обзор элементов управления корпоративным доступом в Yammer в рабочей среде.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332668"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="e8442-103">Элементы управления корпоративным доступом в Yammer</span><span class="sxs-lookup"><span data-stu-id="e8442-103">Yammer enterprise access controls</span></span> 

<span data-ttu-id="e8442-104">Физический и логический доступ к рабочей среде Yammer ограничена небольшим набором людей (инфраструктура и операции).</span><span class="sxs-lookup"><span data-stu-id="e8442-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="e8442-105">Как и другие инженеры Microsoft 365, у специалистов Yammer есть нулевой доступ к данным клиента.</span><span class="sxs-lookup"><span data-stu-id="e8442-105">As with other Microsoft 365 engineers, Yammer engineers have zero standing access to customer data.</span></span> <span data-ttu-id="e8442-106">Доступ должен быть запрошен с помощью системы управления доступом на основе утверждений, как и для защищенного хранилища, с ограниченным количеством утверждающих.</span><span class="sxs-lookup"><span data-stu-id="e8442-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="e8442-107">Утверждающие проверяют запрос (например, проверяют, является ли запрос действительным на основании потребностей, Бизнес-дел, времени и т. д.), а затем Утвердите или отклоните запрос.</span><span class="sxs-lookup"><span data-stu-id="e8442-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="e8442-108">Если запрос утвержден, JIT-доступ предоставляется для определенного и ограниченного времени.</span><span class="sxs-lookup"><span data-stu-id="e8442-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="e8442-109">После превышения времени доступа срок действия доступа истекает автоматически.</span><span class="sxs-lookup"><span data-stu-id="e8442-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="e8442-110">Как и в случае с другими службами Microsoft 365, все доступ к рабочей среде Yammer использует многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e8442-110">As with other Microsoft 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="e8442-111">Все пользователи получают доступ к журналу команд и записываются в журнал и регулярно проверяются группой безопасности Yammer.</span><span class="sxs-lookup"><span data-stu-id="e8442-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="e8442-112">Для получения дополнительных сведений об администрировании и управлении Yammer обратитесь к [справочной статье администратора Yammer](https://docs.microsoft.com/yammer/yammer-landing-page).</span><span class="sxs-lookup"><span data-stu-id="e8442-112">For more information about Yammer administration and management, see [Yammer admin help](https://docs.microsoft.com/yammer/yammer-landing-page).</span></span>