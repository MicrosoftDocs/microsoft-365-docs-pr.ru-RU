---
title: Используйте cmdlets PowerShell для настройки и запуска microsoft Defender AV
description: В Windows 10 вы можете использовать cmdlets PowerShell для запуска сканирования, обновления сведений о безопасности и изменения параметров в антивирусная программа в Microsoft Defender.
keywords: сканирование, командная строка, mpcmdrun, защитник
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765303"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="24929-104">Для настройки и управления антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="24929-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24929-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="24929-105">**Applies to:**</span></span>

- [<span data-ttu-id="24929-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24929-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="24929-107">Вы можете использовать PowerShell для выполнения различных функций в Защитник Windows.</span><span class="sxs-lookup"><span data-stu-id="24929-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="24929-108">Как и командная строка или командная строка, PowerShell — это командная строка на основе задач и язык скриптов, разработанный специально для системного администрирования.</span><span class="sxs-lookup"><span data-stu-id="24929-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="24929-109">Подробнее об этом можно узнать в центре [PowerShell на MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="24929-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="24929-110">Список cmdlets, их функций и доступных параметров см. в разделе [Defender.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="24929-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="24929-111">Cmdlets PowerShell наиболее полезны в среде Windows Server, которая не полагается на графический пользовательский интерфейс (GUI) для настройки программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="24929-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="24929-112">Команды PowerShell не следует использовать в качестве замены для полной инфраструктуры управления сетевой политикой, например [Microsoft Endpoint Configuration Manager,](/configmgr)консоли управления групповой политикой или [шаблонов групповой политики антивирусная программа в Microsoft Defender ADMX.](https://www.microsoft.com/download/101445) [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="24929-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="24929-113">Изменения, внесенные в PowerShell, будут влиять на локальные параметры конечной точки, где эти изменения развернуты или внесены.</span><span class="sxs-lookup"><span data-stu-id="24929-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="24929-114">Это означает, что развертывание политики с помощью групповой политики, Microsoft Endpoint Configuration Manager или Microsoft Intune может переписать изменения, внесенные в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24929-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="24929-115">Можно настроить параметры, которые можно переопределять локально, с помощью [переопределеемых локальных политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="24929-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="24929-116">PowerShell обычно устанавливается в `%SystemRoot%\system32\WindowsPowerShell` папке.</span><span class="sxs-lookup"><span data-stu-id="24929-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="24929-117">Использование антивирусная программа в Microsoft Defender PowerShell</span><span class="sxs-lookup"><span data-stu-id="24929-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="24929-118">В панели Windows поиска введите **powershell**.</span><span class="sxs-lookup"><span data-stu-id="24929-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="24929-119">Выберите **Windows PowerShell** из результатов, чтобы открыть интерфейс.</span><span class="sxs-lookup"><span data-stu-id="24929-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="24929-120">Введите команду PowerShell и любые параметры.</span><span class="sxs-lookup"><span data-stu-id="24929-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="24929-121">Возможно, потребуется открыть PowerShell в режиме администратора.</span><span class="sxs-lookup"><span data-stu-id="24929-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="24929-122">Щелкните правой кнопкой мыши элемент в меню "Пуск", нажмите кнопку **Запустить** в качестве администратора и нажмите **кнопку Да** по запросу разрешений.</span><span class="sxs-lookup"><span data-stu-id="24929-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="24929-123">Чтобы открыть онлайн-справку для любого из пользователей, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="24929-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="24929-124">Ограничь `-online` параметр, чтобы получить локализованную кэшную помощь.</span><span class="sxs-lookup"><span data-stu-id="24929-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="24929-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="24929-125">Related topics</span></span>

- [<span data-ttu-id="24929-126">Справочные темы для средств управления и конфигурации</span><span class="sxs-lookup"><span data-stu-id="24929-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="24929-127">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="24929-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="24929-128">антивирусная программа в Microsoft Defender Cmdlets</span><span class="sxs-lookup"><span data-stu-id="24929-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)