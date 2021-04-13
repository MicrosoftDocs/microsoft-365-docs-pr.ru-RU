---
title: Определите, как мобильные устройства обновляются антивирусом Microsoft Defender
description: Управление обновлением мобильных устройств, таких как ноутбуки, с помощью обновлений антивирусной защиты Microsoft Defender.
keywords: обновления, защита, обновления расписания, батареи, мобильного устройства, ноутбука, ноутбука, выбора, обновления Майкрософт, wsus, переопределения
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690984"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="cd1f6-104">Управление обновлениями для мобильных устройств и виртуальных машин (виртуальных машин)</span><span class="sxs-lookup"><span data-stu-id="cd1f6-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cd1f6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cd1f6-105">**Applies to:**</span></span>

- [<span data-ttu-id="cd1f6-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cd1f6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cd1f6-107">Мобильным устройствам и VM-устройствам может потребоваться больше конфигурации для обеспечения того, чтобы на производительность не повлияли обновления.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="cd1f6-108">Существует два параметра, которые полезны для этих устройств:</span><span class="sxs-lookup"><span data-stu-id="cd1f6-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="cd1f6-109">В приложении Microsoft Update на мобильных компьютерах без подключения wSUS</span><span class="sxs-lookup"><span data-stu-id="cd1f6-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="cd1f6-110">Предотвращение обновлений сведении о безопасности при работе с питанием от батареи</span><span class="sxs-lookup"><span data-stu-id="cd1f6-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="cd1f6-111">В таких ситуациях также могут быть полезны следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="cd1f6-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="cd1f6-112">Настройка запланированных и доголовных сканов</span><span class="sxs-lookup"><span data-stu-id="cd1f6-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cd1f6-113">Управление обновлениями для устарели конечных точек</span><span class="sxs-lookup"><span data-stu-id="cd1f6-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cd1f6-114">Руководство по развертыванию антивируса Microsoft Defender в среде виртуальной инфраструктуры настольных компьютеров (VDI)</span><span class="sxs-lookup"><span data-stu-id="cd1f6-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="cd1f6-115">В приложении Microsoft Update на мобильных компьютерах без подключения wSUS</span><span class="sxs-lookup"><span data-stu-id="cd1f6-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="cd1f6-116">С помощью Microsoft Update можно поддерживать учетную запись безопасности на мобильных устройствах, работающих под управлением антивируса Microsoft Defender, если они не подключены к корпоративной сети или не подключены к WSUS.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="cd1f6-117">Это означает, что обновления защиты можно доставить на устройства (через Microsoft Update), даже если вы задали WSUS переопределение обновления Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="cd1f6-118">Вы можете выбрать microsoft Update на мобильном устройстве одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="cd1f6-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="cd1f6-119">Измените параметр с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="cd1f6-120">Чтобы создать скрипт, используйте VBScript, а затем запустите его на каждом компьютере в сети.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="cd1f6-121">Вручную выберите каждый компьютер в сети через меню **Параметры.**</span><span class="sxs-lookup"><span data-stu-id="cd1f6-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="cd1f6-122">Использование групповой политики для выбора обновления Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cd1f6-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cd1f6-123">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="cd1f6-124">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="cd1f6-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cd1f6-125">Выберите **политики,** а затем **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="cd1f6-126">Расширь дерево до **компонентов Microsoft**  >  **Defender Antivirus** Signature  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="cd1f6-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select **OK.**</span><span class="sxs-lookup"><span data-stu-id="cd1f6-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="cd1f6-128">Используйте VBScript для выбора в Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cd1f6-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cd1f6-129">Используйте инструкции в статье MSDN [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) для создания VBScript.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="cd1f6-130">Запустите VBScript, созданный на каждом компьютере в сети.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="cd1f6-131">Вручную войти в Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="cd1f6-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="cd1f6-132">Откройте **обновление Windows** в & **параметры** безопасности на компьютере, в который вы хотите войти.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="cd1f6-133">Выберите **расширенные** параметры.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="cd1f6-134">Выберите почтовый ящик **Для Дайте мне обновления для других продуктов Майкрософт при обновлении Windows**.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="cd1f6-135">Предотвращение обновлений сведении о безопасности при работе с питанием от батареи</span><span class="sxs-lookup"><span data-stu-id="cd1f6-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="cd1f6-136">Антивирус Microsoft Defender можно настроить только для загрузки обновлений защиты, когда компьютер подключен к проводной источнику питания.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="cd1f6-137">Использование групповой политики для предотвращения обновлений сведений о безопасности на заряде батареи</span><span class="sxs-lookup"><span data-stu-id="cd1f6-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="cd1f6-138">На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, выберите объект групповой политики, который необходимо настроить, и откройте его для редактирования.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="cd1f6-139">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="cd1f6-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="cd1f6-140">Выберите **политики,** а затем **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="cd1f6-141">Развяжите дерево до **компонентов**  >  **Microsoft Defender Antivirus** Signature  >  **Updates,**  а затем установите разрешить обновления сведении безопасности при работе с отключенным питанием **от батареи.**</span><span class="sxs-lookup"><span data-stu-id="cd1f6-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="cd1f6-142">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-142">Then select **OK**.</span></span> 

<span data-ttu-id="cd1f6-143">Это действие предотвращает загрузку обновлений защиты при подзаряжаемом компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd1f6-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cd1f6-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cd1f6-144">Related articles</span></span>

- [<span data-ttu-id="cd1f6-145">Управление обновлениями антивируса Microsoft Defender и применение базовых показателей</span><span class="sxs-lookup"><span data-stu-id="cd1f6-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cd1f6-146">Обновление и управление антивирусом Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="cd1f6-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)