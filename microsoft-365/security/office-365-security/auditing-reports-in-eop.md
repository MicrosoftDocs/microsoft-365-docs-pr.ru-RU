---
title: Отчеты аудита в автономной службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Администраторы могут ознакомиться с отчетами об аудите администраторов, которые доступны в Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205549"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="2ee53-103">Отчеты аудита в автономной службе EOP</span><span class="sxs-lookup"><span data-stu-id="2ee53-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2ee53-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="2ee53-104">**Applies to**</span></span>
-  [<span data-ttu-id="2ee53-105">Автономный exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2ee53-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="2ee53-106">В автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online отчеты аудита могут помочь вам соответствовать требованиям законодательства, соответствия требованиям и судебным разбирательствам для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2ee53-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="2ee53-107">Вы можете получать отчеты аудита в любое время, чтобы определять изменения, внесенные в конфигурацию EOP.</span><span class="sxs-lookup"><span data-stu-id="2ee53-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="2ee53-108">Эти отчеты позволяют устранять неполадки конфигурации и определять причины проблем, связанных с обеспечением защиты или соблюдением требований.</span><span class="sxs-lookup"><span data-stu-id="2ee53-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="2ee53-109">В автономных отчетах EOP доступны два отчета аудита:</span><span class="sxs-lookup"><span data-stu-id="2ee53-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="2ee53-110">**Отчет группы ролей администратора.** Отчет группы ролей администратора позволяет просматривать, когда пользователь добавляется или удаляется из членства в группе ролей администратора.</span><span class="sxs-lookup"><span data-stu-id="2ee53-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="2ee53-111">С помощью этого отчета вы сможете отслеживать изменения в разрешениях администратора, назначенных пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2ee53-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="2ee53-112">Дополнительные сведения см. в [примере Run an administrator role group report in standalone EOP.](run-an-administrator-role-group-report-in-eop-eop.md)</span><span class="sxs-lookup"><span data-stu-id="2ee53-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="2ee53-113">**Журнал аудита** администратора. Журнал аудита администратора записи любых действий (на основе автономных cmdlets EOP PowerShell) администратором или пользователем с административными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="2ee53-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="2ee53-114">Дополнительные сведения см. в [журнале аудита администратора в Exchange Online.](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)</span><span class="sxs-lookup"><span data-stu-id="2ee53-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>