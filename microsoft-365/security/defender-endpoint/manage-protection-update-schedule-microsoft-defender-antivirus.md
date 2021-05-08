---
title: Расписание антивирусная программа в Microsoft Defender обновлений защиты
description: Расписание дня, времени и интервала для загрузки обновлений защиты
keywords: обновления, базовые показатели безопасности, расписание обновлений
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275040"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="a89b0-104">Управление расписанием загрузки и применения обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a89b0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a89b0-105">**Applies to:**</span></span>

- [<span data-ttu-id="a89b0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a89b0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a89b0-107">антивирусная программа в Microsoft Defender позволяет определить, когда следует искать и загружать обновления.</span><span class="sxs-lookup"><span data-stu-id="a89b0-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="a89b0-108">Вы можете запланировать обновления для конечных точек по:</span><span class="sxs-lookup"><span data-stu-id="a89b0-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="a89b0-109">Указание дня недели для проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="a89b0-110">Указание интервала для проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="a89b0-111">Указание времени проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="a89b0-112">Вы также можете рандомизировать время, когда каждая конечная точка проверяет и скачивает обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="a89b0-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="a89b0-113">Дополнительные [сведения см. в](scheduled-catch-up-scans-microsoft-defender-antivirus.md) разделе Проверка расписания.</span><span class="sxs-lookup"><span data-stu-id="a89b0-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="a89b0-114">Использование диспетчера конфигурации для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="a89b0-115">На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ,  которые необходимо изменить (щелкните Активы и соответствие требованиям в области навигации слева, а затем разогнайте дерево до Endpoint Protection  >    >  **antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="a89b0-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="a89b0-116">Перейдите в **раздел Обновления сведении безопасности.**</span><span class="sxs-lookup"><span data-stu-id="a89b0-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="a89b0-117">Проверка и загрузка обновлений в определенное время:</span><span class="sxs-lookup"><span data-stu-id="a89b0-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="a89b0-118">Установите проверку Endpoint Protection обновлений разведки безопасности **с определенным интервалом...** до **0**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="a89b0-119">Установите проверку Endpoint Protection обновлений разведки безопасности ежедневно **по времени проверки** обновлений.</span><span class="sxs-lookup"><span data-stu-id="a89b0-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="a89b0-120">3</span><span class="sxs-lookup"><span data-stu-id="a89b0-120">3</span></span>
4. <span data-ttu-id="a89b0-121">Для проверки и загрузки обновлений на непрерывном интервале установите Endpoint Protection обновления сведении безопасности за определенный **интервал...** до количества часов, которые должны происходить между обновлениями.</span><span class="sxs-lookup"><span data-stu-id="a89b0-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="a89b0-122">[Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="a89b0-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="a89b0-123">Использование групповой политики для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a89b0-124">По умолчанию антивирусная программа в Microsoft Defender будет проверять обновление за 15 минут до времени запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="a89b0-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="a89b0-125">Включение этих параметров переопределит этот по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a89b0-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="a89b0-126">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="a89b0-127">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="a89b0-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="a89b0-128">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="a89b0-129">Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**  >  **signature Intelligence Updates** и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a89b0-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="a89b0-130">Дважды нажмите кнопку **Укажите** день недели, чтобы проверить параметр обновления сведении безопасности и задать параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a89b0-131">Введите день недели, чтобы проверить обновления.</span><span class="sxs-lookup"><span data-stu-id="a89b0-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="a89b0-132">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-132">Click **OK**.</span></span>
    2. <span data-ttu-id="a89b0-133">Дважды нажмите кнопку **Укажите интервал для проверки** параметров обновлений разведки безопасности и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="a89b0-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a89b0-134">Введите количество часов между обновлениями.</span><span class="sxs-lookup"><span data-stu-id="a89b0-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="a89b0-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-135">Click **OK**.</span></span>
    3. <span data-ttu-id="a89b0-136">Дважды щелкните **кнопку Укажите время** для проверки параметра обновлений разведки безопасности и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="a89b0-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a89b0-137">Введите время проверки обновлений.</span><span class="sxs-lookup"><span data-stu-id="a89b0-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="a89b0-138">Время основано на локальном времени конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a89b0-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="a89b0-139">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a89b0-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="a89b0-140">Использование cmdlets PowerShell для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="a89b0-141">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a89b0-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="a89b0-142">Дополнительные сведения о том, как использовать [PowerS антивирусная программа в Microsoft Defender hell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусная программа в Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="a89b0-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="a89b0-143">Используйте Windows управления (WMI) для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a89b0-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="a89b0-144">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="a89b0-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="a89b0-145">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="a89b0-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="a89b0-146">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="a89b0-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="a89b0-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a89b0-147">Related articles</span></span>

- [<span data-ttu-id="a89b0-148">Развертывание антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a89b0-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a89b0-149">Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="a89b0-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a89b0-150">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="a89b0-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a89b0-151">Управление принудительными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="a89b0-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a89b0-152">Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)</span><span class="sxs-lookup"><span data-stu-id="a89b0-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a89b0-153">антивирусная программа в Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="a89b0-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)