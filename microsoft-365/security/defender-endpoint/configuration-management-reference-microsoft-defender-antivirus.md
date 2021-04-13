---
title: Управление Защитник Windows бизнесом
description: Узнайте, как использовать групповую политику, диспетчер конфигурации, PowerShell, WMI, Intune и командную строку для управления AV Microsoft Defender
keywords: групповой политики, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, security, protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad3e8d2fb61eb5a2a350d061f926dd7bff8ae109
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691074"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="26727-104">Управление антивирусом Microsoft Defender в вашем бизнесе</span><span class="sxs-lookup"><span data-stu-id="26727-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="26727-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="26727-105">**Applies to:**</span></span>

- [<span data-ttu-id="26727-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="26727-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="26727-107">Вы можете управлять и настраивать антивирус Microsoft Defender с помощью следующих средств:</span><span class="sxs-lookup"><span data-stu-id="26727-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="26727-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (теперь входит в состав Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="26727-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="26727-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (теперь является частью Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="26727-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="26727-110">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="26727-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="26727-111">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="26727-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="26727-112">Инструментарий управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="26727-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="26727-113">Командная [строка Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (именуемая как *mpcmdrun.exe* утилита</span><span class="sxs-lookup"><span data-stu-id="26727-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="26727-114">В следующих статьях данная статья предоставляет дополнительные сведения, ссылки и ресурсы для использования этих средств для управления и настройки антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="26727-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="26727-115">Статья</span><span class="sxs-lookup"><span data-stu-id="26727-115">Article</span></span> | <span data-ttu-id="26727-116">Описание</span><span class="sxs-lookup"><span data-stu-id="26727-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="26727-117">Управление антивирусом Microsoft Defender с помощью Microsoft Intune и Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="26727-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="26727-118">Сведения об использовании Intune и Configuration Manager для развертывания, управления, отчета и настройки антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="26727-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="26727-119">Управление антивирусом Microsoft Defender с помощью параметров групповой политики</span><span class="sxs-lookup"><span data-stu-id="26727-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="26727-120">Список всех параметров групповой политики, расположенных в шаблонах ADMX</span><span class="sxs-lookup"><span data-stu-id="26727-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="26727-121">Управление антивирусной программой Microsoft Defender с помощью cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="26727-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="26727-122">Инструкции по использованию команды PowerShell для управления антивирусом Microsoft Defender, а также ссылки на документацию для всех cmdlets и разрешенных параметров</span><span class="sxs-lookup"><span data-stu-id="26727-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="26727-123">Управление антивирусом Microsoft Defender с помощью инструментов управления Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="26727-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="26727-124">Инструкции по использованию WMI для управления антивирусом Microsoft Defender, а также ссылки на документацию для API WMIv2 (включая все классы, методы и свойства)</span><span class="sxs-lookup"><span data-stu-id="26727-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="26727-125">Управление антивирусом Microsoft Defender с помощью mpcmdrun.exe командной строки</span><span class="sxs-lookup"><span data-stu-id="26727-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="26727-126">Инструкции по использованию специального средства командной строки для управления и использования антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="26727-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |