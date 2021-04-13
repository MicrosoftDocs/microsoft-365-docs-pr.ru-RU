---
title: Расписание обновлений антивирусной защиты Защитника Майкрософт
description: Расписание дня, времени и интервала для загрузки обновлений защиты
keywords: обновления, базовые показатели безопасности, расписание обновлений
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691029"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="a6002-104">Управление расписанием загрузки и приложения обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a6002-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a6002-105">**Applies to:**</span></span>

- [<span data-ttu-id="a6002-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a6002-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a6002-107">Антивирус Microsoft Defender позволяет определить, когда следует искать и скачивать обновления.</span><span class="sxs-lookup"><span data-stu-id="a6002-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="a6002-108">Вы можете запланировать обновления для конечных точек по:</span><span class="sxs-lookup"><span data-stu-id="a6002-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="a6002-109">Указание дня недели для проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="a6002-110">Указание интервала для проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="a6002-111">Указание времени проверки обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="a6002-112">Вы также можете рандомизировать время, когда каждая конечная точка проверяет и скачивает обновления защиты.</span><span class="sxs-lookup"><span data-stu-id="a6002-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="a6002-113">Дополнительные [сведения см. в](scheduled-catch-up-scans-microsoft-defender-antivirus.md) разделе Проверка расписания.</span><span class="sxs-lookup"><span data-stu-id="a6002-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="a6002-114">Использование диспетчера конфигурации для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="a6002-115">На консоли Microsoft Endpoint Manager откройте политику противомалярийных программ, которые необходимо изменить (нажмите кнопку Активы и соответствие требованиям в области навигации слева, а затем расширите дерево до Обзор политики защиты конечных   >    >  точек)</span><span class="sxs-lookup"><span data-stu-id="a6002-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="a6002-116">Перейдите в **раздел Обновления сведении безопасности.**</span><span class="sxs-lookup"><span data-stu-id="a6002-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="a6002-117">Проверка и загрузка обновлений в определенное время:</span><span class="sxs-lookup"><span data-stu-id="a6002-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="a6002-118">Установите **проверку сведений о** безопасности endpoint Protection с определенным интервалом... до **0**.</span><span class="sxs-lookup"><span data-stu-id="a6002-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="a6002-119">Установите проверку для обновления сведений о безопасности конечной точки защиты ежедневно **по времени проверки** обновлений.</span><span class="sxs-lookup"><span data-stu-id="a6002-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="a6002-120">3</span><span class="sxs-lookup"><span data-stu-id="a6002-120">3</span></span>
4. <span data-ttu-id="a6002-121">Для проверки и загрузки обновлений с непрерывным интервалом установите проверку сведений о безопасности **endpoint Protection** с определенным интервалом до количества часов, которые должны происходить между обновлениями.</span><span class="sxs-lookup"><span data-stu-id="a6002-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="a6002-122">[Развертывание обновленной политики в обычном режиме.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="a6002-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="a6002-123">Использование групповой политики для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6002-124">Антивирус Microsoft Defender по умолчанию проверяет обновление за 15 минут до времени запланированного сканирования.</span><span class="sxs-lookup"><span data-stu-id="a6002-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="a6002-125">Включение этих параметров переопределит этот по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6002-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="a6002-126">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a6002-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="a6002-127">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="a6002-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="a6002-128">Щелкните **Политики,** а **затем административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="a6002-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="a6002-129">Расширь дерево на **компоненты**  >  **Microsoft Defender Antivirus Signature** Intelligence  >  **Updates** и настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a6002-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="a6002-130">Дважды нажмите кнопку **Укажите** день недели, чтобы проверить параметр обновления сведении безопасности и задать параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="a6002-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a6002-131">Введите день недели, чтобы проверить обновления.</span><span class="sxs-lookup"><span data-stu-id="a6002-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="a6002-132">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6002-132">Click **OK**.</span></span>
    2. <span data-ttu-id="a6002-133">Дважды нажмите кнопку **Укажите интервал для проверки** параметров обновлений разведки безопасности и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="a6002-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a6002-134">Введите количество часов между обновлениями.</span><span class="sxs-lookup"><span data-stu-id="a6002-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="a6002-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6002-135">Click **OK**.</span></span>
    3. <span data-ttu-id="a6002-136">Дважды щелкните **кнопку Укажите время** для проверки параметра обновлений разведки безопасности и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="a6002-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a6002-137">Введите время проверки обновлений.</span><span class="sxs-lookup"><span data-stu-id="a6002-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="a6002-138">Время основано на локальном времени конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a6002-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="a6002-139">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6002-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="a6002-140">Использование cmdlets PowerShell для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="a6002-141">Используйте следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a6002-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="a6002-142">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)  с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="a6002-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="a6002-143">Использование инструкции по управлению Windows (WMI) для расписания обновлений защиты</span><span class="sxs-lookup"><span data-stu-id="a6002-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="a6002-144">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="a6002-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="a6002-145">Дополнительные сведения и допустимые параметры см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="a6002-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="a6002-146">Защитник Windows API WMIv2</span><span class="sxs-lookup"><span data-stu-id="a6002-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="a6002-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a6002-147">Related articles</span></span>

- [<span data-ttu-id="a6002-148">Развертывание антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a6002-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6002-149">Управление обновлениями антивируса Microsoft Defender и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="a6002-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6002-150">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="a6002-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6002-151">Управление вынужденными обновлениями на основе событий</span><span class="sxs-lookup"><span data-stu-id="a6002-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6002-152">Управление обновлениями для мобильных устройств и виртуальных машин (виртуальных машин)</span><span class="sxs-lookup"><span data-stu-id="a6002-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a6002-153">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6002-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)