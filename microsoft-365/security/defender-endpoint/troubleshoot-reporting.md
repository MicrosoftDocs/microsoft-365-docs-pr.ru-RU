---
title: Устранение неполадок с средствами отчетности для microsoft Defender AV
description: Определение и решение распространенных проблем при попытке сообщить в microsoft Defender av protection status in Update Compliance
keywords: устранение неполадок, ошибка, исправление, обновление соответствия требованиям, oms, монитор, отчет, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764535"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="1e60e-104">Устранение неполадок с отчетами антивирусной программы в Microsoft Defender в соответствии с требованиями обновлений</span><span class="sxs-lookup"><span data-stu-id="1e60e-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1e60e-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1e60e-105">**Applies to:**</span></span>

- [<span data-ttu-id="1e60e-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1e60e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="1e60e-107">31 марта 2020 г. функция антивирусной отчетности Microsoft Defender в соответствии с обновлениями будет удалена.</span><span class="sxs-lookup"><span data-stu-id="1e60e-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="1e60e-108">Вы можете продолжать определять и пересматривать политики соответствия требованиям безопасности с помощью [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)что позволяет более точно контролировать функции безопасности и обновления.</span><span class="sxs-lookup"><span data-stu-id="1e60e-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="1e60e-109">Антивирус Microsoft Defender можно использовать с соблюдением требований к обновлению.</span><span class="sxs-lookup"><span data-stu-id="1e60e-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="1e60e-110">Вы увидите состояние лицензий E3, B, F1, VL и Pro.</span><span class="sxs-lookup"><span data-stu-id="1e60e-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="1e60e-111">Однако для лицензий E5 необходимо использовать портал [Microsoft Defender для конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="1e60e-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="1e60e-112">Дополнительные информацию о вариантах лицензирования см. в [меню Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="1e60e-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="1e60e-113">При использовании соответствия требованиям обновления [Windows Analytics](/windows/deployment/update/update-compliance-using#wdav-assessment) для получения отчетов о состоянии защиты устройств или конечных точек в сети, использующих антивирус Microsoft Defender, могут возникнуть проблемы или проблемы.</span><span class="sxs-lookup"><span data-stu-id="1e60e-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="1e60e-114">Как правило, наиболее распространенными показателями проблемы являются:</span><span class="sxs-lookup"><span data-stu-id="1e60e-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="1e60e-115">Вы видите только небольшое число или подмножество всех устройств, которые вы ожидали увидеть</span><span class="sxs-lookup"><span data-stu-id="1e60e-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="1e60e-116">Вы не видите никаких устройств вообще</span><span class="sxs-lookup"><span data-stu-id="1e60e-116">You do not see any devices at all</span></span>
- <span data-ttu-id="1e60e-117">Отчеты и сведения, которые вы видите, устарели (старше нескольких дней)</span><span class="sxs-lookup"><span data-stu-id="1e60e-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="1e60e-118">Общие коды ошибок и коды событий, относящиеся к антивирусной службе Microsoft Defender, не связанные с соответствием требованиям к обновлению, см. в [веб-сайте События](troubleshoot-microsoft-defender-antivirus.md)антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1e60e-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="1e60e-119">Устранение этих проблем можно решить тремя шагами.</span><span class="sxs-lookup"><span data-stu-id="1e60e-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="1e60e-120">Подтверждение того, что вы выполнили все необходимые условия</span><span class="sxs-lookup"><span data-stu-id="1e60e-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="1e60e-121">Проверка подключения к облачной Защитник Windows службе</span><span class="sxs-lookup"><span data-stu-id="1e60e-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="1e60e-122">Отправка журналов поддержки</span><span class="sxs-lookup"><span data-stu-id="1e60e-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="1e60e-123">Обычно для начала появления устройств в обновлении требуется 3 дня.</span><span class="sxs-lookup"><span data-stu-id="1e60e-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="1e60e-124">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="1e60e-124">Confirm prerequisites</span></span>

<span data-ttu-id="1e60e-125">Для правильного показа устройств в обновлении необходимо выполнить определенные требования как для службы соответствия требованиям обновления, так и для антивируса Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="1e60e-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="1e60e-126">Конечные точки используют антивирус Microsoft Defender в качестве единственного приложения для защиты от антивирусов.</span><span class="sxs-lookup"><span data-stu-id="1e60e-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="1e60e-127">[Использование любого другого антивирусного приложения](microsoft-defender-antivirus-compatibility.md) приведет к отключению microsoft Defender AV, а конечная точка не будет отчитаться в обновлении.</span><span class="sxs-lookup"><span data-stu-id="1e60e-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="1e60e-128">[Включена облачная защита.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1e60e-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="1e60e-129">Конечные точки могут [подключаться к облаку AV Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="1e60e-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="1e60e-130">Если конечная точка работает под управлением Windows 10 версии 1607 или более ранней версии, диагностические данные Windows 10 должны быть задарены на [расширенном уровне.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)</span><span class="sxs-lookup"><span data-stu-id="1e60e-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="1e60e-131">Прошло 3 дня с тех пор, как все требования были выполнены</span><span class="sxs-lookup"><span data-stu-id="1e60e-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="1e60e-132">"Вы можете использовать антивирус Microsoft Defender с обновлением соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1e60e-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="1e60e-133">Вы увидите состояние лицензий E3, B, F1, VL и Pro.</span><span class="sxs-lookup"><span data-stu-id="1e60e-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="1e60e-134">Однако для лицензий E5 необходимо использовать портал Microsoft Defender для конечных точек https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) (.</span><span class="sxs-lookup"><span data-stu-id="1e60e-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="1e60e-135">Дополнительные информацию о вариантах лицензирования см. в дополнительных версиях лицензирования продуктов Windows 10"</span><span class="sxs-lookup"><span data-stu-id="1e60e-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="1e60e-136">Если все вышеперечисленные условия выполнены, может потребоваться перейти к следующему шагу для сбора диагностических сведений и отправки их нам.</span><span class="sxs-lookup"><span data-stu-id="1e60e-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1e60e-137">Сбор диагностических данных для устранения неполадок в соответствии с соответствием требованиям.</span><span class="sxs-lookup"><span data-stu-id="1e60e-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="1e60e-138">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1e60e-138">Related topics</span></span>

- [<span data-ttu-id="1e60e-139">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="1e60e-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="1e60e-140">Развертывание антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1e60e-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)