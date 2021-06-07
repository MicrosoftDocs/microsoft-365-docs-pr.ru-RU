---
title: Настройка возможностей уменьшения поверхности атаки
description: Для настройки уменьшения поверхности атаки используйте Microsoft Intune, Microsoft Endpoint Configuration Manager, powerShell и групповой политики.
keywords: asr, уменьшение поверхности атаки, защитник Windows, защитник Microsoft, антивирус, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770965"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="0d0fb-104">Настройка возможностей уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="0d0fb-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="0d0fb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0d0fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="0d0fb-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0d0fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0d0fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d0fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="0d0fb-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0d0fb-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="0d0fb-109">[Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="0d0fb-110">Defender for Endpoint включает несколько возможностей уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="0d0fb-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="0d0fb-111">Дополнительные сведения см. в обзоре возможностей уменьшения [поверхности атаки.](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="0d0fb-112">Чтобы настроить уменьшение поверхности атаки в среде, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0d0fb-112">To configure attack surface reduction in your environment, follow these steps:</span></span> 

1. <span data-ttu-id="0d0fb-113">[Включить аппаратную изоляцию для Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="0d0fb-114">Включить управление приложениями.</span><span class="sxs-lookup"><span data-stu-id="0d0fb-114">Enable application control.</span></span> 

   1. <span data-ttu-id="0d0fb-115">Просмотрите базовые политики в Windows.</span><span class="sxs-lookup"><span data-stu-id="0d0fb-115">Review base policies in Windows.</span></span> <span data-ttu-id="0d0fb-116">Примеры [базовых политик](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span><span class="sxs-lookup"><span data-stu-id="0d0fb-116">See [example base policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="0d0fb-117">См. [руководство по разработке управления приложениями.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-117">See the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="0d0fb-118">Обратитесь к руководству [по разработке управления приложениями.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-118">Refer to the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="0d0fb-119">[Включить управляемый доступ к папке](enable-controlled-folders.md).</span><span class="sxs-lookup"><span data-stu-id="0d0fb-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="0d0fb-120">[Включаем защиту сети.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="0d0fb-121">[Включить защиту эксплойтов.](enable-exploit-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="0d0fb-122">[Настройка правил уменьшения поверхности атаки.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="0d0fb-123">Настройка сетевого брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="0d0fb-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="0d0fb-124">Получите обзор брандмауэр Защитника Windows [с расширенным обеспечением безопасности.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="0d0fb-125">Руководство по [разработке брандмауэр Защитника Windows](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) для разработки политик брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="0d0fb-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="0d0fb-126">Используйте руководство [брандмауэр Защитника Windows развертывания](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) для настройки брандмауэра организации с расширенным обеспечением безопасности.</span><span class="sxs-lookup"><span data-stu-id="0d0fb-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span> 

> [!TIP]
> <span data-ttu-id="0d0fb-127">В большинстве случаев при настройке возможностей уменьшения поверхности атаки можно выбрать один из нескольких методов:</span><span class="sxs-lookup"><span data-stu-id="0d0fb-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>
> - <span data-ttu-id="0d0fb-128">Microsoft Endpoint Manager (которая теперь включает Microsoft Intune и Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="0d0fb-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="0d0fb-129">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="0d0fb-129">Group Policy</span></span>
> - <span data-ttu-id="0d0fb-130">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d0fb-130">PowerShell cmdlets</span></span>
