---
title: Развертывание и включение антивирусной программы в Microsoft Defender
description: Развертывание антивируса Microsoft Defender для защиты конечных точек с помощью Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell и WMI.
keywords: развертывание, включить, антивирус Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 146447f4036d800832c75c7a59978e9571253a17
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764823"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="b0a51-104">Развертывание и включение антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0a51-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b0a51-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b0a51-105">**Applies to:**</span></span>

- [<span data-ttu-id="b0a51-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b0a51-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b0a51-107">В зависимости от используемой системы управления может потребоваться включить или настроить антивирусную защиту Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b0a51-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="b0a51-108">В таблице [Развертывание,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) управление и отчет по антивирусу Microsoft Defender см. инструкции по защите с помощью Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell и Инструкции по управлению Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="b0a51-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="b0a51-109">В некоторых сценариях требуются дополнительные рекомендации по успешному развертыванию или настройке антивирусной защиты Microsoft Defender, например среды виртуальной инфраструктуры настольных компьютеров (VDI).</span><span class="sxs-lookup"><span data-stu-id="b0a51-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="b0a51-110">Оставшаяся статья в этом разделе содержит рекомендации и рекомендации по настройке антивируса Microsoft Defender на виртуальных машинах (виртуальных машинах) в среде VDI или [Remote Desktop Services (RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b0a51-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b0a51-111">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b0a51-111">Related articles</span></span>

- [<span data-ttu-id="b0a51-112">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="b0a51-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b0a51-113">Развертывание, управление обновлениями и отчет об антивирусе Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0a51-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b0a51-114">Руководство по развертыванию антивирусной программы в Microsoft Defender в среде инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="b0a51-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)