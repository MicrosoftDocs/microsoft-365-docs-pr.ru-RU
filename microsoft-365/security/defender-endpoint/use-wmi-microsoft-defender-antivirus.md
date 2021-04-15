---
title: Настройка антивируса Microsoft Defender с помощью WMI
description: Узнайте, как настроить и управлять антивирусом Microsoft Defender с помощью скриптов WMI для получения, изменения и обновления параметров в Microsoft Defender для конечной точки.
keywords: wmi, скрипты, инструменты управления Windows, конфигурация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764067"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="38b19-104">Использование инструментов управления Windows (WMI) для настройки и управления антивирусной программой Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38b19-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="38b19-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="38b19-105">**Applies to:**</span></span>

- [<span data-ttu-id="38b19-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="38b19-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="38b19-107">Инструментарий управления Windows (WMI) — это интерфейс скриптирования, который позволяет получать, изменять и обновлять параметры.</span><span class="sxs-lookup"><span data-stu-id="38b19-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="38b19-108">Узнайте больше о WMI в [библиотеке Microsoft Developer Network администрирования системы](/windows/win32/wmisdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="38b19-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="38b19-109">Антивирус Microsoft Defender имеет ряд определенных классов WMI, которые можно использовать для выполнения большинства тех же функций, что и групповые политики и другие средства управления.</span><span class="sxs-lookup"><span data-stu-id="38b19-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="38b19-110">Многие классы аналогичны [cmdlets Defender PowerShell.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="38b19-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="38b19-111">Справочная [библиотека поставщиков Защитник Windows WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) содержит списки доступных классов WMI для антивируса Microsoft Defender и включает примеры сценариев.</span><span class="sxs-lookup"><span data-stu-id="38b19-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="38b19-112">Изменения, внесенные в WMI, повлияют на локальные параметры конечной точки, где эти изменения развернуты или внесены.</span><span class="sxs-lookup"><span data-stu-id="38b19-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="38b19-113">Это означает, что развертывание политики с помощью групповой политики, Microsoft Endpoint Configuration Manager или Microsoft Intune может переписать изменения, внесенные с помощью WMI.</span><span class="sxs-lookup"><span data-stu-id="38b19-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="38b19-114">Можно настроить параметры, которые можно переопределять локально, с помощью [переопределеемых локальных политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="38b19-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="38b19-115">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="38b19-115">Related topics</span></span>

- [<span data-ttu-id="38b19-116">Справочные темы для средств управления и конфигурации</span><span class="sxs-lookup"><span data-stu-id="38b19-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="38b19-117">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="38b19-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)