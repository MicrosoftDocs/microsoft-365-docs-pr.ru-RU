---
title: Загружаемое средство проверки оценки готовности
description: Проверяет параметры устройства и сети, включая необходимые конечные точки
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581038"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="29215-104">Загружаемое средство проверки оценки готовности</span><span class="sxs-lookup"><span data-stu-id="29215-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="29215-105">Чтобы хорошо работать с компьютеры, управляемые Майкрософт, устройства должны соответствовать определенным требованиям к оборудованию и настройкам.</span><span class="sxs-lookup"><span data-stu-id="29215-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="29215-106">Кроме того, каждое устройство должно иметь возможность достичь конечных точек ключей.</span><span class="sxs-lookup"><span data-stu-id="29215-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="29215-107">Скачайте и запустите этот инструмент, чтобы получить HTML-отчет, просмотреть результаты и принять меры.</span><span class="sxs-lookup"><span data-stu-id="29215-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="29215-108">Вам потребуется скачать инструмент и вспомогательные файлы, а затем запустить его вручную на каждом устройстве, которое вы хотите зарегистрировать в компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="29215-109">Для каждой проверки средство будет сообщать об одном из трех возможных результатов:</span><span class="sxs-lookup"><span data-stu-id="29215-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="29215-110">Результат</span><span class="sxs-lookup"><span data-stu-id="29215-110">Result</span></span>  |<span data-ttu-id="29215-111">Смысл</span><span class="sxs-lookup"><span data-stu-id="29215-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="29215-112">Ready</span><span class="sxs-lookup"><span data-stu-id="29215-112">Ready</span></span>     | <span data-ttu-id="29215-113">До завершения регистрации не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="29215-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="29215-114">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="29215-114">Advisory</span></span>    | <span data-ttu-id="29215-115">Следуйте шагам в инструменте для наилучшего опыта с регистрацией и для пользователей.</span><span class="sxs-lookup"><span data-stu-id="29215-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="29215-116">Вы *можете* завершить регистрацию, но перед развертыванием первого устройства необходимо устранить эти проблемы.</span><span class="sxs-lookup"><span data-stu-id="29215-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="29215-117">Не готов</span><span class="sxs-lookup"><span data-stu-id="29215-117">Not ready</span></span> | <span data-ttu-id="29215-118">*Если вы* не исправите эти проблемы, регистрация не состоится.</span><span class="sxs-lookup"><span data-stu-id="29215-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="29215-119">Выполните действия в инструменте для их устранения.</span><span class="sxs-lookup"><span data-stu-id="29215-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="29215-120">Получение шайки</span><span class="sxs-lookup"><span data-stu-id="29215-120">Obtain the checker</span></span>

<span data-ttu-id="29215-121">Скачайте .zip файл https://aka.ms/mmddratoolv0 из .</span><span class="sxs-lookup"><span data-stu-id="29215-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="29215-122">Пользователь, запуская средство, должен иметь локальные права администратора на устройстве, где он работает.</span><span class="sxs-lookup"><span data-stu-id="29215-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="29215-123">Затем запустите средство, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="29215-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="29215-124">Скопируйте загруженный .zip на каждое устройство, которое необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="29215-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="29215-125">Извлеките все файлы в сжатой загрузке.</span><span class="sxs-lookup"><span data-stu-id="29215-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="29215-126">Запуск **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="29215-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="29215-127">Когда появится подсказка управления доступом пользователей, выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="29215-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="29215-128">Средство запускает и открывает отчет в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="29215-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="29215-129">Можно также скачать и извлечь архив .zip общего расположения, получить **доступ** Microsoft.MMD.DeviceReadinessAssessmentTool.exeс каждого устройства, а затем запустить его локально.</span><span class="sxs-lookup"><span data-stu-id="29215-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="29215-130">Проверки</span><span class="sxs-lookup"><span data-stu-id="29215-130">Checks</span></span>

<span data-ttu-id="29215-131">Загружаемый инструмент проверяет эти элементы, связанные с устройством и сетью:</span><span class="sxs-lookup"><span data-stu-id="29215-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="29215-132">Оборудование</span><span class="sxs-lookup"><span data-stu-id="29215-132">Hardware</span></span>

<span data-ttu-id="29215-133">Устройства должны соответствовать определенным требованиям к оборудованию для работы с компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="29215-134">В настоящее [время](../service-description/device-list.md) разрешена регистрация только определенных утвержденных устройств.</span><span class="sxs-lookup"><span data-stu-id="29215-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="29215-135">Если устройство не совместимо с проверками, оно не совместимо с компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="29215-136">Конечные точки сети</span><span class="sxs-lookup"><span data-stu-id="29215-136">Network endpoints</span></span>

<span data-ttu-id="29215-137">Устройства могут достигать нескольких [ключевых конечных](network.md) точек для работы с компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="29215-138">Если средство сообщает не **готовый** результат, см. подробный отчет, чтобы узнать, какие конечные точки недоступны.</span><span class="sxs-lookup"><span data-stu-id="29215-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="29215-139">Затем настройте брандмауэр или другие сетевые параметры, чтобы обеспечить возможность доступа к этим конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="29215-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="29215-140">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="29215-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="29215-141">Enterprise профилей Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="29215-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="29215-142">Результат **консультации** означает, что вы используете некоторые профили Wi-Fi, для правильной работы с помощью сертификатов и профилей.</span><span class="sxs-lookup"><span data-stu-id="29215-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="29215-143">Дополнительные сведения см. в [странице Развертывание сертификатов и профиля Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="29215-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="29215-144">LAN-профили</span><span class="sxs-lookup"><span data-stu-id="29215-144">LAN profiles</span></span>

<span data-ttu-id="29215-145">Результат **advisory** означает, что у вас есть службы безопасности, для правильной работы с помощью сертификатов и профилей.</span><span class="sxs-lookup"><span data-stu-id="29215-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="29215-146">Дополнительные сведения см. в [странице Подготовка сертификатов](certs-wifi-lan.md)и сетевых профилей для компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="29215-147">ПРОФИЛИ VPN</span><span class="sxs-lookup"><span data-stu-id="29215-147">VPN profiles</span></span>

<span data-ttu-id="29215-148">Результат **advisory** означает, что вы используете виртуальную частную сеть (VPN).</span><span class="sxs-lookup"><span data-stu-id="29215-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="29215-149">Создайте VPN-профиль, который развертывает сертификаты, интегрированные с Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="29215-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="29215-150">Дополнительные сведения см. в [странице Подготовка сертификатов](certs-wifi-lan.md)и сетевых профилей для компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="29215-151">Mapped drives</span><span class="sxs-lookup"><span data-stu-id="29215-151">Mapped drives</span></span>

<span data-ttu-id="29215-152">Результат **advisory** означает, что у вас есть несколько картографных дисков, которые не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="29215-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="29215-153">Дополнительные сведения см. в [руб. Подготовка с картами](mapped-drives.md)дисков для компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29215-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="29215-154">Печать очередей</span><span class="sxs-lookup"><span data-stu-id="29215-154">Print queues</span></span>

<span data-ttu-id="29215-155">Результат **Advisory** означает, что у вас есть несколько очередей для печати, которые не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="29215-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="29215-156">Одним из решений является использование облачной печати.</span><span class="sxs-lookup"><span data-stu-id="29215-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="29215-157">Дополнительные сведения см. в [публикации Prepare printing resources for компьютеры, управляемые Майкрософт.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="29215-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="29215-158">Прокси</span><span class="sxs-lookup"><span data-stu-id="29215-158">Proxies</span></span>

<span data-ttu-id="29215-159">Результат **advisory** означает, что у вас есть прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="29215-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="29215-160">Дополнительные сведения см. в [сетевой конфигурации для компьютеры, управляемые Майкрософт.](network.md)</span><span class="sxs-lookup"><span data-stu-id="29215-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

