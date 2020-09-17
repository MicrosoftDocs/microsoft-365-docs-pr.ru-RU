---
title: Аналитика центра безопасности Windows
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 772d1d52e977a067ff9bc3517de9cb2ae6c8c9a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950371"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="882b8-103">Аналитика центра безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="882b8-103">Windows security update insights</span></span>
<span data-ttu-id="882b8-104">В этом представлении представлен обзор состояния обновлений для системы безопасности для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="882b8-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="882b8-105">Чтобы просмотреть данные об использовании, перейдите на вкладку <strong>обновления для системы безопасности Windows</strong> .</span><span class="sxs-lookup"><span data-stu-id="882b8-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Область обновления для системы безопасности Windows: линейчатые графики состояния устройства и версии обновления в левом столбце, обновление процесса развертывания со временем в центральном столбце и процент активных устройств по группам развертывания, а также количество дней, затраченных на доступ к целевому элементу развертывания %95% в правом столбце.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="882b8-107">Состояние устройства</span><span class="sxs-lookup"><span data-stu-id="882b8-107">Device status</span></span>

<span data-ttu-id="882b8-108">Чтобы устройства обновлялись с помощью центра обновления Windows, они должны быть подключены к Интернету без перехода в режим гибернации не менее шести часов, два из которых должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="882b8-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="882b8-109">Пока устройство подключено и не находится в спящем режиме, оно считается "используемым".</span><span class="sxs-lookup"><span data-stu-id="882b8-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="882b8-110">Несмотря на то, что обновление устройства, которое не соответствует этим требованиям, невозможно, устройства, соответствующие им, могут быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="882b8-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="882b8-111">Мы классифицированы действия устройств в контексте центра обновления Windows с помощью следующих условий:</span><span class="sxs-lookup"><span data-stu-id="882b8-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="882b8-112"><strong>Active:</strong> Устройства, которые удовлетворяют минимальным критериям использования (шесть часов, два непрерывных) для последнего выпуска обновления для системы безопасности и возвращены в Microsoft Intune по крайней мере каждые пять дней</span><span class="sxs-lookup"><span data-stu-id="882b8-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="882b8-113"><strong>Синхронизация:</strong> Устройства, которые были возвращены с помощью Intune в течение последних 28 дней</span><span class="sxs-lookup"><span data-stu-id="882b8-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="882b8-114">Не <strong>синхронизировано:</strong> Устройства, которые <i>не</i> были возвращены в Intune за последние 28 дней</span><span class="sxs-lookup"><span data-stu-id="882b8-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="882b8-115">Обновление состояния версии</span><span class="sxs-lookup"><span data-stu-id="882b8-115">Update version status</span></span>

<span data-ttu-id="882b8-116">Корпорация Майкрософт выпускает обновления для системы безопасности каждый второй вторник месяца.</span><span class="sxs-lookup"><span data-stu-id="882b8-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="882b8-117">Каждый выпуск добавляет важные обновления для известных уязвимостей системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="882b8-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="882b8-118">Настольные компьютеры, управляемые Майкрософт, гарантируют, что 95% управляемых устройств обновляются последними доступными обновлениями для системы безопасности каждый месяц.</span><span class="sxs-lookup"><span data-stu-id="882b8-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="882b8-119">Обновления для системы безопасности иногда выпускаются в другое время для срочного решения новых угроз.</span><span class="sxs-lookup"><span data-stu-id="882b8-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="882b8-120">На настольном компьютере с управляемым Майкрософт эти обновления развертываются аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="882b8-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="882b8-121">Мы будем классифицировать состояние обновлений системы безопасности, выполнив следующие условия:</span><span class="sxs-lookup"><span data-stu-id="882b8-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="882b8-122"><strong>Current:</strong> Устройства, на которых выполняется обновление, выпущенное в текущем месяце</span><span class="sxs-lookup"><span data-stu-id="882b8-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="882b8-123"><strong>Previous:</strong> Устройства, на которых запущено обновление, выпущенное за предыдущий месяц</span><span class="sxs-lookup"><span data-stu-id="882b8-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="882b8-124"><strong>Более старая версия:</strong> Устройства с обновлениями для системы безопасности, выпущенные до предыдущего месяца</span><span class="sxs-lookup"><span data-stu-id="882b8-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="882b8-125">В <strong>старой</strong> категории должны приводиться несколько устройств, что может привести к возникновению проблем с системой, которые следует отследить на рабочем столе Майкрософт, чтобы мы могли исследовать эту проблему.</span><span class="sxs-lookup"><span data-stu-id="882b8-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="882b8-126">Ход развертывания</span><span class="sxs-lookup"><span data-stu-id="882b8-126">Deployment progress</span></span>

<span data-ttu-id="882b8-127">В начале каждого цикла обновления для системы безопасности на рабочем столе, управляемом Майкрософт, создается снимок заполнения устройства и задается цель развертывания на 95% от этого заполнения.</span><span class="sxs-lookup"><span data-stu-id="882b8-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="882b8-128">В области <strong>ход выполнения развертывания</strong> показан исторический тренд, который обновлялся ежедневно, отслеживая, насколько близко развертывание обновления соответствует этому целевому объекту для каждого выпуска.</span><span class="sxs-lookup"><span data-stu-id="882b8-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="882b8-129">На этом графике показаны только устройства с активным состоянием.</span><span class="sxs-lookup"><span data-stu-id="882b8-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="882b8-130">Вы можете просмотреть эти данные для предыдущих циклов обновления с помощью раскрывающегося меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="882b8-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="882b8-131">Период, выбранный в этом меню, применяется ко всем сведениям на всей странице.</span><span class="sxs-lookup"><span data-stu-id="882b8-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="882b8-132">Область <strong>обновленных активных устройств с помощью группы развертывания</strong> предоставляет другое представление, отображая ход установки обновления для каждой из групп развертывания на настольных компьютерах, управляемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="882b8-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="882b8-133">Область " <strong>дни для достижения целевого</strong> значения" показывает, сколько времени заняло 95% от общего числа устройств, которые будут обновлены с учетом текущего обновления для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="882b8-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="882b8-134">Пока выполняется развертывание, эта область <strong>по-прежнему будет обновляться</strong> до тех пор, пока не будет достигнута цель 95% для выбранного обновления.</span><span class="sxs-lookup"><span data-stu-id="882b8-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="882b8-135">Область сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="882b8-135">Device details area</span></span>

<span data-ttu-id="882b8-136">В нижней части панели мониторинга находится таблица с подробными сведениями об устройствах, в том числе о [состоянии устройства](#device-status) и [статусе версии обновления](#update-version-status).</span><span class="sxs-lookup"><span data-stu-id="882b8-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="882b8-137">Вы можете выполнить поиск в этом списке или отфильтровать его по любому значению в списке.</span><span class="sxs-lookup"><span data-stu-id="882b8-137">You can search this list or filter it by any listed value.</span></span>


![Таблица сведений об устройстве, в которой показаны столбцы для имени устройства, назначенного пользователя, состояния устройства, версии обновления, версии операционной системы и даты последней синхронизации устройства.](../../media/security-update-insights-device-table-sterile.png)
