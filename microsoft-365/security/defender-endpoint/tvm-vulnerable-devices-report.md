---
title: Отчет об уязвимых устройствах — контроль угроз и уязвимостей
description: Отчет, в котором показаны уязвимые тенденции устройства и текущая статистика. Цель состоит в том, чтобы вы понимали дыхание и область экспозиции устройства.
keywords: Microsoft Defender для уязвимых устройств Endpoint-tvm, Microsoft Defender для конечной точки, tvm, снижение риска & уязвимости, снижение угрозы и уязвимости, мониторинг конфигурации безопасности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245484"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="ae096-105">Отчет об уязвимых устройствах — контроль угроз и уязвимостей</span><span class="sxs-lookup"><span data-stu-id="ae096-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ae096-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ae096-106">**Applies to:**</span></span>

- [<span data-ttu-id="ae096-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ae096-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ae096-108">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="ae096-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ae096-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae096-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ae096-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ae096-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ae096-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ae096-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="ae096-112">В отчете показаны графики и диаграммы с уязвимыми тенденциями устройства и текущей статистикой.</span><span class="sxs-lookup"><span data-stu-id="ae096-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="ae096-113">Цель состоит в том, чтобы вы понимали дыхание и область экспозиции устройства.</span><span class="sxs-lookup"><span data-stu-id="ae096-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="ae096-114">Доступ к отчету в Центр безопасности в Microsoft Defender с помощью отчетов > **уязвимых устройств**</span><span class="sxs-lookup"><span data-stu-id="ae096-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="ae096-115">Существует два столбца:</span><span class="sxs-lookup"><span data-stu-id="ae096-115">There are two columns:</span></span>

- <span data-ttu-id="ae096-116">Тенденции (со временем).</span><span class="sxs-lookup"><span data-stu-id="ae096-116">Trends (over time).</span></span> <span data-ttu-id="ae096-117">Может показывать последние 30 дней, 3 месяца, 6 месяцев или настраиваемый диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="ae096-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="ae096-118">Сегодня (текущая информация)</span><span class="sxs-lookup"><span data-stu-id="ae096-118">Today (current information)</span></span>

<span data-ttu-id="ae096-119">**Фильтр.** Можно фильтровать данные по уровням серьезности уязвимости, доступности эксплуатации, возрасту уязвимости, платформе операционной системы, Windows 10 версии или группе устройств.</span><span class="sxs-lookup"><span data-stu-id="ae096-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="ae096-120">**Сверлить.** Если необходимо изучить дополнительные сведения, выберите соответствующую планку, чтобы просмотреть отфильтрованный список устройств на странице инвентаризации устройств.</span><span class="sxs-lookup"><span data-stu-id="ae096-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="ae096-121">Оттуда можно экспортировать список.</span><span class="sxs-lookup"><span data-stu-id="ae096-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="ae096-122">Графы уровня серьезности</span><span class="sxs-lookup"><span data-stu-id="ae096-122">Severity level graphs</span></span>

<span data-ttu-id="ae096-123">Каждое устройство считается только один раз в соответствии с самой серьезной уязвимостью, найденной на этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="ae096-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Один график текущих уровней серьезности уязвимости устройства и один график, показывающий уровни с течением времени.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="ae096-125">Использование графиков доступности</span><span class="sxs-lookup"><span data-stu-id="ae096-125">Exploit availability graphs</span></span>

<span data-ttu-id="ae096-126">Каждое устройство считается только один раз на основе самого высокого уровня известного эксплойта.</span><span class="sxs-lookup"><span data-stu-id="ae096-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Один график доступности эксплуатации текущего устройства и один график, показывающий доступность с течением времени.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="ae096-128">Графики возраста уязвимости</span><span class="sxs-lookup"><span data-stu-id="ae096-128">Vulnerability age graphs</span></span>

<span data-ttu-id="ae096-129">Каждое устройство считается только один раз в соответствии с самой старой датой публикации уязвимости.</span><span class="sxs-lookup"><span data-stu-id="ae096-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="ae096-130">Более старые уязвимости имеют более высокую вероятность использования.</span><span class="sxs-lookup"><span data-stu-id="ae096-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Один график текущего возраста уязвимости устройства и один график, показывающий возраст с течением времени.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="ae096-132">Уязвимые устройства с помощью графиков платформ операционной системы</span><span class="sxs-lookup"><span data-stu-id="ae096-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="ae096-133">Количество устройств на каждой операционной системе, которые подвергаются воздействию уязвимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="ae096-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Один график текущих уязвимых устройств с помощью платформы операционной системы и один график, показывающий уязвимые устройства на платформах ОС с течением времени.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="ae096-135">Уязвимые устройства по Windows 10 графиков версий</span><span class="sxs-lookup"><span data-stu-id="ae096-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="ae096-136">Количество устройств на каждой Windows 10, которые подвергаются воздействию уязвимых приложений или ОС.</span><span class="sxs-lookup"><span data-stu-id="ae096-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Один график текущих уязвимых устройств по Windows 10 версии и один график, показывающий уязвимые устройства по Windows 10 версии с течением времени.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="ae096-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ae096-138">Related topics</span></span>

- [<span data-ttu-id="ae096-139">Обзор угроз и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="ae096-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ae096-140">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="ae096-140">Security recommendations</span></span>](tvm-security-recommendation.md)
