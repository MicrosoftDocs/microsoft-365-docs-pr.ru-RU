---
title: Аналитика центра безопасности Windows
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739838"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="a1dae-103">Аналитика центра безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="a1dae-103">Windows security update insights</span></span>
<span data-ttu-id="a1dae-104">В этом представлении представлен обзор состояния обновлений безопасности для компьютеры, управляемые Майкрософт устройств.</span><span class="sxs-lookup"><span data-stu-id="a1dae-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="a1dae-105">Чтобы просмотреть данные об использовании, <strong>выберите вкладку Windows обновлений безопасности.</strong></span><span class="sxs-lookup"><span data-stu-id="a1dae-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windows области обновления безопасности: штрих-графики состояния устройства и версии обновления в левом столбце, обновление хода развертывания со временем в центре столбца, а также процент активных устройств по группе развертывания, а также количество дней, за которые нужно достичь цели развертывания 95% в правой колонке.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="a1dae-107">Состояние устройства</span><span class="sxs-lookup"><span data-stu-id="a1dae-107">Device status</span></span>

<span data-ttu-id="a1dae-108">Чтобы устройства обновлялись в Windows Update, они должны подключаться к Интернету и не в течение шести часов, причем два из них должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="a1dae-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="a1dae-109">Несмотря на то, что возможно обновление устройства, не отвечающее этим требованиям, устройства, которые соответствуют им, имеют самую высокую вероятность обновления.</span><span class="sxs-lookup"><span data-stu-id="a1dae-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="a1dae-110">Мы классифицировать действия устройств в контексте Windows обновления с помощью этих терминов:</span><span class="sxs-lookup"><span data-stu-id="a1dae-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="a1dae-111"><strong>Active:</strong> Устройства, которые выполнили минимальные критерии активности (шесть часов, два непрерывных) для последнего выпуска обновлений безопасности и регистрались в Microsoft Intune по крайней мере каждые пять дней.</span><span class="sxs-lookup"><span data-stu-id="a1dae-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="a1dae-112"><strong>Синхронизировано:</strong> Устройства, зарегистрированные в Intune в течение последних 28 дней</span><span class="sxs-lookup"><span data-stu-id="a1dae-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="a1dae-113"><strong>Не синхронизируйтесь:</strong> Устройства, <i>не зарегистрированные</i> в Intune за последние 28 дней</span><span class="sxs-lookup"><span data-stu-id="a1dae-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="a1dae-114">Обновление состояния версии</span><span class="sxs-lookup"><span data-stu-id="a1dae-114">Update version status</span></span>

<span data-ttu-id="a1dae-115">Корпорация Майкрософт выпускает обновления безопасности каждый второй вторник месяца.</span><span class="sxs-lookup"><span data-stu-id="a1dae-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="a1dae-116">Каждый выпуск добавляет важные обновления для известных уязвимостей безопасности.</span><span class="sxs-lookup"><span data-stu-id="a1dae-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="a1dae-117">компьютеры, управляемые Майкрософт гарантирует, что 95% управляемых устройств обновляются с помощью последнего обновления безопасности каждый месяц.</span><span class="sxs-lookup"><span data-stu-id="a1dae-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="a1dae-118">Обновления безопасности иногда выпускаются в другое время для срочного устранения новых угроз.</span><span class="sxs-lookup"><span data-stu-id="a1dae-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="a1dae-119">компьютеры, управляемые Майкрософт развертывает эти обновления аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="a1dae-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="a1dae-120">Мы классифицировать состояние версий обновления безопасности с помощью этих терминов:</span><span class="sxs-lookup"><span data-stu-id="a1dae-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="a1dae-121"><strong>Current:</strong> Устройства, которые запускают обновление, выпущенное в текущем месяце</span><span class="sxs-lookup"><span data-stu-id="a1dae-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="a1dae-122"><strong>Предыдущие:</strong> Устройства, работающие с обновлением, которое было выпущено в предыдущем месяце</span><span class="sxs-lookup"><span data-stu-id="a1dae-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="a1dae-123"><strong>Более старые:</strong> Устройства, работающие с любым обновлением безопасности, выпущенным до предыдущего месяца</span><span class="sxs-lookup"><span data-stu-id="a1dae-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="a1dae-124">Вы должны увидеть несколько <strong></strong> устройств в старой категории — большое или растущее население, вероятно, указывает на системную проблему, о которую следует сообщать в компьютеры, управляемые Майкрософт, чтобы мы могли исследовать.</span><span class="sxs-lookup"><span data-stu-id="a1dae-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="a1dae-125">Ход развертывания</span><span class="sxs-lookup"><span data-stu-id="a1dae-125">Deployment progress</span></span>

<span data-ttu-id="a1dae-126">В начале каждого цикла выпуска обновления безопасности компьютеры, управляемые Майкрософт снимок населения устройства и задает целевой показатель развертывания в 95% от этого населения.</span><span class="sxs-lookup"><span data-stu-id="a1dae-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="a1dae-127">Область <strong>выполнения развертывания показывает</strong> исторический тренд, обновляемый ежедневно, отслеживая, насколько близко развертывание обновлений соответствует этой цели для каждого выпуска.</span><span class="sxs-lookup"><span data-stu-id="a1dae-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="a1dae-128">На этом графике показаны только устройства с активным состоянием.</span><span class="sxs-lookup"><span data-stu-id="a1dae-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="a1dae-129">Эти данные можно просмотреть для предыдущих циклов обновления с помощью меню отсев в правом верхнем справа.</span><span class="sxs-lookup"><span data-stu-id="a1dae-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="a1dae-130">Период, выбранный в этом меню, относится ко всем сведениям на всей странице.</span><span class="sxs-lookup"><span data-stu-id="a1dae-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="a1dae-131">Обновленные <strong>активные устройства</strong> по области группы развертывания предлагают другое представление, показывая ход установки обновления для каждой из компьютеры, управляемые Майкрософт развертывания.</span><span class="sxs-lookup"><span data-stu-id="a1dae-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="a1dae-132">Дни <strong>достижения целевой</strong> области отображают, сколько времени потребовалось для 95% от общего числа устройств, которые будут обновлены с текущим обновлением безопасности.</span><span class="sxs-lookup"><span data-stu-id="a1dae-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="a1dae-133">Пока развертывание продолжается, в <strong></strong> этой области отображается обновление до тех пор, пока не будет достигнута цель 95% для выбранного обновления.</span><span class="sxs-lookup"><span data-stu-id="a1dae-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="a1dae-134">Область сведений о устройстве</span><span class="sxs-lookup"><span data-stu-id="a1dae-134">Device details area</span></span>

<span data-ttu-id="a1dae-135">В нижней части панели мониторинга находится таблица с [](#device-status) подробными сведениями для устройств, включая состояние устройства и состояние [версии обновления.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="a1dae-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="a1dae-136">Вы можете искать этот список или фильтровать его любым перечисленным значением.</span><span class="sxs-lookup"><span data-stu-id="a1dae-136">You can search this list or filter it by any listed value.</span></span>


![Таблица сведений о устройстве, показывающая столбцы для имени устройства, назначенного пользователя, состояния устройства, версии обновления, версии операционной системы и даты последней синхронизации устройства.](../../media/security-update-insights-device-table-sterile.png)
