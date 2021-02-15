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
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941445"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="97102-103">Аналитика центра безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="97102-103">Windows security update insights</span></span>
<span data-ttu-id="97102-104">В этом представлении представлен обзор состояния обновлений системы безопасности для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="97102-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="97102-105">Чтобы просмотреть данные об использовании, выберите вкладку <strong>"Обновления для системы безопасности Windows".</strong></span><span class="sxs-lookup"><span data-stu-id="97102-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Области обновлений для системы безопасности Windows: диаграммы состояния устройства и версии обновления в левом столбце, ход развертывания обновлений со временем в центральном столбце и процент активных устройств по группе развертывания, а также количество дней, за которые нужно достичь целевого показателя развертывания на 95 % в правом столбце.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="97102-107">Состояние устройства</span><span class="sxs-lookup"><span data-stu-id="97102-107">Device status</span></span>

<span data-ttu-id="97102-108">Чтобы устройства обновлялись с помощью Обновления Windows, они должны быть подключены к Интернету и не в режиме гибернации в течение не менее шести часов, два из которых должны быть непрерывными.</span><span class="sxs-lookup"><span data-stu-id="97102-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="97102-109">Несмотря на то, что устройство, не отвечающее этим требованиям, может быть обновлено, но устройства, которые их соответствуют, имеют самую высокую вероятность обновления.</span><span class="sxs-lookup"><span data-stu-id="97102-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="97102-110">Мы классифицировать действия с устройствами в контексте Обновления Windows с помощью указанных здесь условий.</span><span class="sxs-lookup"><span data-stu-id="97102-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="97102-111"><strong>Активные:</strong> Устройства, которые соответствуют минимальным условиям активности (шесть часов, два непрерывных) для последнего выпуска обновлений для системы безопасности и выполнили регистрацию в Microsoft Intune не реже чем раз в пять дней</span><span class="sxs-lookup"><span data-stu-id="97102-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="97102-112"><strong>Синхронизировано:</strong> Устройства, которые зарегистрировались с помощью Intune за последние 28 дней</span><span class="sxs-lookup"><span data-stu-id="97102-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="97102-113"><strong>Не синхронизировано:</strong> Устройства, которые <i>не были</i> зарегистрированы в Intune в течение последних 28 дней</span><span class="sxs-lookup"><span data-stu-id="97102-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="97102-114">Обновление состояния версии</span><span class="sxs-lookup"><span data-stu-id="97102-114">Update version status</span></span>

<span data-ttu-id="97102-115">Корпорация Майкрософт выпускает обновления для системы безопасности каждый второй вторник месяца.</span><span class="sxs-lookup"><span data-stu-id="97102-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="97102-116">Каждый выпуск добавляет важные обновления для известных уязвимостей безопасности.</span><span class="sxs-lookup"><span data-stu-id="97102-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="97102-117">Компьютеры, управляемые Майкрософт, обеспечивают ежемесячное обновление 95 % управляемых устройств с помощью последних доступных обновлений для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="97102-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="97102-118">Иногда обновления для системы безопасности выпускаются в другое время для экстренного устранения новых угроз.</span><span class="sxs-lookup"><span data-stu-id="97102-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="97102-119">Компьютеры, управляемые Майкрософт, развертывают эти обновления аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="97102-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="97102-120">Мы классифицировать состояние версий обновления для системы безопасности с помощью указанных здесь условий.</span><span class="sxs-lookup"><span data-stu-id="97102-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="97102-121"><strong>Текущие:</strong> Устройства с обновлением, выпущенным в текущем месяце</span><span class="sxs-lookup"><span data-stu-id="97102-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="97102-122"><strong>Предыдущий:</strong> Устройства с обновлением, выпущенным в предыдущем месяце</span><span class="sxs-lookup"><span data-stu-id="97102-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="97102-123"><strong>Более старые:</strong> Устройства с любым обновлением для системы безопасности, выпущенным до предыдущего месяца</span><span class="sxs-lookup"><span data-stu-id="97102-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="97102-124">В категории "Старые" должно быть мало устройств. Большой или растущий объем пользователей, вероятно, указывает на системную проблему, о которую необходимо сообщить на компьютер, управляемый Майкрософт, чтобы мы могли изучить этот вопрос. <strong></strong></span><span class="sxs-lookup"><span data-stu-id="97102-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="97102-125">Ход развертывания</span><span class="sxs-lookup"><span data-stu-id="97102-125">Deployment progress</span></span>

<span data-ttu-id="97102-126">В начале каждого цикла выпуска обновлений для системы безопасности на компьютере, управляемом Майкрософт, создается моментальный снимок аудитории устройства и устанавливается целевой целевой показатель развертывания для 95 % этой аудитории.</span><span class="sxs-lookup"><span data-stu-id="97102-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="97102-127">В <strong>области хода</strong> развертывания показана история тенденций, обновляемая ежедневно, отслеживая, насколько близко развертывание обновлений соответствует этому целевому показателю для каждого выпуска.</span><span class="sxs-lookup"><span data-stu-id="97102-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="97102-128">На этом графике показаны только устройства с активным состоянием.</span><span class="sxs-lookup"><span data-stu-id="97102-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="97102-129">Вы можете просмотреть эти данные для предыдущих циклов обновления с помощью меню в правом верхнем меню.</span><span class="sxs-lookup"><span data-stu-id="97102-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="97102-130">Период, выбранный в этом меню, применяется ко всем сведениям на всей странице.</span><span class="sxs-lookup"><span data-stu-id="97102-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="97102-131">Обновленные <strong>активные устройства</strong> по области группы развертывания отличаются представлением о ходе установки обновлений для каждой группы развертывания управляемых Майкрософт компьютеров.</span><span class="sxs-lookup"><span data-stu-id="97102-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="97102-132">Дни <strong>достижения целевой</strong> области показывают, сколько времени потребовалось для 95 % от общего количества устройств, обновляемого с помощью текущего обновления для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="97102-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="97102-133">Во время развертывания в этой <strong></strong> области отображается обновление до тех пор, пока не будет достигнут целевой показатель 95 % для выбранного обновления.</span><span class="sxs-lookup"><span data-stu-id="97102-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="97102-134">Область сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="97102-134">Device details area</span></span>

<span data-ttu-id="97102-135">В нижней части панели мониторинга отображается таблица с [](#device-status) подробными сведениями о ваших устройствах, включая состояние устройства и состояние [версии обновления.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="97102-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="97102-136">Этот список можно найти или отфильтровать по любому из перечисленных значений.</span><span class="sxs-lookup"><span data-stu-id="97102-136">You can search this list or filter it by any listed value.</span></span>


![Таблица сведений об устройстве, в которой показаны столбцы для имени устройства, назначенного пользователя, состояния устройства, версии обновления, версии операционной системы и даты последней синхронизации устройства.](../../media/security-update-insights-device-table-sterile.png)
