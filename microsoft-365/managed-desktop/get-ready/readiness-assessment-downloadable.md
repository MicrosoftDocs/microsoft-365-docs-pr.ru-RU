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
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922024"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="6ac84-104">Загружаемое средство проверки оценки готовности</span><span class="sxs-lookup"><span data-stu-id="6ac84-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="6ac84-105">Чтобы хорошо работать с настольными компьютерами, управляемыми Майкрософт, устройства должны соответствовать определенным требованиям к оборудованию и настройкам.</span><span class="sxs-lookup"><span data-stu-id="6ac84-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="6ac84-106">Кроме того, каждое устройство должно иметь возможность достичь ключевых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="6ac84-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="6ac84-107">Скачайте и запустите это средство, чтобы получить HTML-отчет, просмотреть результаты, а затем выполнить действия.</span><span class="sxs-lookup"><span data-stu-id="6ac84-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="6ac84-108">Вам потребуется скачать средство и вспомогательные файлы, а затем запустить его вручную на каждом устройстве, которое вы хотите зарегистрировать на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6ac84-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6ac84-109">Для каждой проверки средство сообщает один из трех возможных результатов:</span><span class="sxs-lookup"><span data-stu-id="6ac84-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="6ac84-110">Результат</span><span class="sxs-lookup"><span data-stu-id="6ac84-110">Result</span></span>  |<span data-ttu-id="6ac84-111">Смысл</span><span class="sxs-lookup"><span data-stu-id="6ac84-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="6ac84-112">Ready</span><span class="sxs-lookup"><span data-stu-id="6ac84-112">Ready</span></span>     | <span data-ttu-id="6ac84-113">Перед завершением регистрации никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="6ac84-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="6ac84-114">Консультации</span><span class="sxs-lookup"><span data-stu-id="6ac84-114">Advisory</span></span>    | <span data-ttu-id="6ac84-115">Следуйте шагам в средстве для наилучшего опыта регистрации и для пользователей.</span><span class="sxs-lookup"><span data-stu-id="6ac84-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="6ac84-116">Вы *можете* завершить регистрацию, но перед развертыванием первого устройства необходимо устранить эти проблемы.</span><span class="sxs-lookup"><span data-stu-id="6ac84-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="6ac84-117">Не готово</span><span class="sxs-lookup"><span data-stu-id="6ac84-117">Not ready</span></span> | <span data-ttu-id="6ac84-118">*Если не устранить* эти проблемы, регистрация не удастся.</span><span class="sxs-lookup"><span data-stu-id="6ac84-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="6ac84-119">Выполните действия в средстве, чтобы устранить их.</span><span class="sxs-lookup"><span data-stu-id="6ac84-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="6ac84-120">Получение контрольного</span><span class="sxs-lookup"><span data-stu-id="6ac84-120">Obtain the checker</span></span>

<span data-ttu-id="6ac84-121">Скачайте ZIP-файл из https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="6ac84-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="6ac84-122">Пользователь, запуская средство, должен иметь права локального администратора на устройстве, на котором оно запущено.</span><span class="sxs-lookup"><span data-stu-id="6ac84-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="6ac84-123">Затем запустите средство, вы выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6ac84-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="6ac84-124">Скопируйте скачаный ZIP-файл на каждое устройство, которое нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="6ac84-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="6ac84-125">Извлеките все файлы в сжатой загрузке.</span><span class="sxs-lookup"><span data-stu-id="6ac84-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="6ac84-126">Запустите **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="6ac84-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="6ac84-127">Когда появится запрос на управление доступом пользователей, выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="6ac84-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="6ac84-128">Средство запускается и открывает отчет в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ac84-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="6ac84-129">Вы также можете скачать и извлечь ZIP-архив в общее расположение, получить доступ **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** с каждого устройства, а затем запустить его локально.</span><span class="sxs-lookup"><span data-stu-id="6ac84-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="6ac84-130">Проверки</span><span class="sxs-lookup"><span data-stu-id="6ac84-130">Checks</span></span>

<span data-ttu-id="6ac84-131">Скачиваемые средства проверяют эти элементы, связанные с устройством и сетью:</span><span class="sxs-lookup"><span data-stu-id="6ac84-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="6ac84-132">Оборудование</span><span class="sxs-lookup"><span data-stu-id="6ac84-132">Hardware</span></span>

<span data-ttu-id="6ac84-133">Устройства должны соответствовать определенным требованиям к оборудованию для работы с настольными компьютерами, управляемыми Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6ac84-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="6ac84-134">В настоящее время только определенные [утвержденные устройства](../service-description/device-list.md) могут быть зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="6ac84-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="6ac84-135">Если устройство не совместимо ни с одной из проверок, оно несовместимо с компьютером, управляемым Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6ac84-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="6ac84-136">Конечные точки сети</span><span class="sxs-lookup"><span data-stu-id="6ac84-136">Network endpoints</span></span>

<span data-ttu-id="6ac84-137">Устройства могут получить несколько основных конечных [точек](network.md) для работы с компьютерами, управляемыми Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6ac84-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6ac84-138">Если средство сообщает о не **готовых** результатах, см. подробный отчет, чтобы узнать, какие конечные точки недоступны.</span><span class="sxs-lookup"><span data-stu-id="6ac84-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="6ac84-139">Затем настройте брандмауэр или другие параметры сети, чтобы обеспечить возможность доступа к этим конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="6ac84-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="6ac84-140">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="6ac84-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="6ac84-141">Корпоративные профили Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6ac84-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="6ac84-142">Результат **консультации** означает, что вы используете некоторые профили Wi-Fi, которые требуют сертификатов и профилей для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="6ac84-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="6ac84-143">Дополнительные сведения см. в справке по развертыванию сертификатов и профилю [Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="6ac84-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="6ac84-144">Профили локальной сети</span><span class="sxs-lookup"><span data-stu-id="6ac84-144">LAN profiles</span></span>

<span data-ttu-id="6ac84-145">Результат **консультации** означает, что у вас есть сети lans, которые требуют сертификатов и профилей для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="6ac84-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="6ac84-146">Дополнительные сведения см. в [подготовьте сертификаты и сетевые профили для компьютеров, управляемых Майкрософт.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="6ac84-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="6ac84-147">Профили VPN</span><span class="sxs-lookup"><span data-stu-id="6ac84-147">VPN profiles</span></span>

<span data-ttu-id="6ac84-148">Результат **консультации** означает, что вы используете виртуальную частную сеть (VPN).</span><span class="sxs-lookup"><span data-stu-id="6ac84-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="6ac84-149">Создайте профиль VPN, который развертывает сертификаты, интегрированные с Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6ac84-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="6ac84-150">Дополнительные сведения см. в [подготовьте сертификаты и сетевые профили для компьютеров, управляемых Майкрософт.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="6ac84-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="6ac84-151">Mapped drives</span><span class="sxs-lookup"><span data-stu-id="6ac84-151">Mapped drives</span></span>

<span data-ttu-id="6ac84-152">Результат **консультации** означает, что у вас есть некоторые диски, которые не рекомендуется использовать.</span><span class="sxs-lookup"><span data-stu-id="6ac84-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="6ac84-153">Дополнительные сведения см. в [подготовьте mapped drives for Microsoft Managed Desktop.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="6ac84-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="6ac84-154">Очереди печати</span><span class="sxs-lookup"><span data-stu-id="6ac84-154">Print queues</span></span>

<span data-ttu-id="6ac84-155">Результат **консультации** означает, что у вас есть некоторые очереди печати, которые не рекомендуется использовать.</span><span class="sxs-lookup"><span data-stu-id="6ac84-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="6ac84-156">Одним из решений является использование облачной печати.</span><span class="sxs-lookup"><span data-stu-id="6ac84-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="6ac84-157">Дополнительные сведения см. в [подготовьте ресурсы печати для компьютеров, управляемых Майкрософт.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="6ac84-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="6ac84-158">Прокси-прокси</span><span class="sxs-lookup"><span data-stu-id="6ac84-158">Proxies</span></span>

<span data-ttu-id="6ac84-159">Результат **консультации** означает, что используется прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6ac84-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="6ac84-160">Дополнительные сведения см. в [конфигурации сети для компьютеров, управляемых Майкрософт.](network.md)</span><span class="sxs-lookup"><span data-stu-id="6ac84-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

