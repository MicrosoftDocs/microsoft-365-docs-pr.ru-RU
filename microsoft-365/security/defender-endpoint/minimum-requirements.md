---
title: Минимальные требования к Microsoft Defender для конечной точки
description: Понимание требований и требований лицензирования для бортовых устройств к службе
keywords: минимальные требования, лицензирование, таблица сравнения
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6607d5029e45c77754a431c87eb61cd281e013c1
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730730"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="3e0d3-104">Минимальные требования к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e0d3-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e0d3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-105">**Applies to:**</span></span>

- [<span data-ttu-id="3e0d3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e0d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3e0d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e0d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3e0d3-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3e0d3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3e0d3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="3e0d3-110">Для бортовых устройств к службе существует несколько минимальных требований.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="3e0d3-111">Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для бортовых устройств службы.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="3e0d3-112">Узнайте о последних улучшениях в Defender for Endpoint: [Defender for Endpoint Tech Community.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="3e0d3-113">Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="3e0d3-114">Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="3e0d3-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="3e0d3-115">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="3e0d3-115">Licensing requirements</span></span>

<span data-ttu-id="3e0d3-116">Microsoft Defender для конечной точки требует одно из следующих предложений по лицензированию томов Корпорации Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="3e0d3-117">Windows 10 Корпоративная E5</span><span class="sxs-lookup"><span data-stu-id="3e0d3-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="3e0d3-118">Windows 10 для образовательных учреждений A5</span><span class="sxs-lookup"><span data-stu-id="3e0d3-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="3e0d3-119">Microsoft 365 E5 (M365 E5), которая включает Windows 10 Корпоративная E5</span><span class="sxs-lookup"><span data-stu-id="3e0d3-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="3e0d3-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="3e0d3-121">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3e0d3-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="3e0d3-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="3e0d3-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="3e0d3-123">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e0d3-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d3-124">Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="3e0d3-125">Microsoft Defender для конечной точки также доступен для покупки в поставщик облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="3e0d3-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="3e0d3-126">Для VMs RDSH не требуется отдельная лицензия Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="3e0d3-127">Microsoft Defender для конечной точки для серверов требует одного из следующих вариантов лицензирования:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="3e0d3-128">Центр безопасности Azure с включенной службой Защитник Azure</span><span class="sxs-lookup"><span data-stu-id="3e0d3-128">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="3e0d3-129">Microsoft Defender для конечной точки для сервера (по одной на закрытый сервер)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d3-130">Клиенты могут приобретать лицензии на серверы (по одной на крытую среду операционной системы сервера)для Microsoft Defender для конечной точки для серверов, если у них есть совокупный минимум 50 лицензий для одной или более из следующих лицензий пользователей:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="3e0d3-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3e0d3-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="3e0d3-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="3e0d3-132">Windows E5/A5</span></span>
> * <span data-ttu-id="3e0d3-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="3e0d3-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="3e0d3-134">Microsoft 365 E5/A5 Security</span><span class="sxs-lookup"><span data-stu-id="3e0d3-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="3e0d3-135">Подробные сведения о лицензировании см. на [сайте Условия](https://www.microsoft.com/licensing/terms/) продукта и поработать с командой учетных записей, чтобы узнать больше об условиях и условиях.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="3e0d3-136">Дополнительные сведения о массиве функций в Windows 10 выпусках см. в [Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="3e0d3-137">Подробную таблицу сравнения сравнения Windows 10 коммерческого выпуска см. в таблице [сравнения PDF.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="3e0d3-138">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="3e0d3-138">Browser requirements</span></span>

<span data-ttu-id="3e0d3-139">Доступ к Защитнику для конечной точки делается через браузер, поддерживая следующие браузеры:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="3e0d3-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3e0d3-140">Microsoft Edge</span></span>
- <span data-ttu-id="3e0d3-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="3e0d3-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d3-142">Хотя другие браузеры могут работать, указанные браузеры поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="3e0d3-143">Требования к оборудованию и программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="3e0d3-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="3e0d3-144">Поддерживаемые Windows версии</span><span class="sxs-lookup"><span data-stu-id="3e0d3-144">Supported Windows versions</span></span>

- <span data-ttu-id="3e0d3-145">Windows 7 sp1 Enterprise[(требуется ESU для поддержки.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-145">Windows 7 SP1 Enterprise ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="3e0d3-146">Windows 7 sp1 Pro[(требуется ESU для поддержки.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-146">Windows 7 SP1 Pro ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="3e0d3-147">Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="3e0d3-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="3e0d3-148">Windows 8.1 Профессиональная</span><span class="sxs-lookup"><span data-stu-id="3e0d3-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="3e0d3-149">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="3e0d3-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="3e0d3-150">Windows 10 Корпоративная LTSC 2016 (или более позднее)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-150">Windows 10 Enterprise LTSC 2016 (or later)</span></span>](/windows/whats-new/ltsc/)
- <span data-ttu-id="3e0d3-151">Windows 10 для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="3e0d3-151">Windows 10 Education</span></span>
- <span data-ttu-id="3e0d3-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="3e0d3-152">Windows 10 Pro</span></span>
- <span data-ttu-id="3e0d3-153">Windows 10 Pro для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="3e0d3-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="3e0d3-154">Windows сервер</span><span class="sxs-lookup"><span data-stu-id="3e0d3-154">Windows server</span></span>
  - <span data-ttu-id="3e0d3-155">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="3e0d3-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3e0d3-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="3e0d3-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3e0d3-157">Windows Server 2016</span></span>
  - <span data-ttu-id="3e0d3-158">Windows Сервер, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="3e0d3-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="3e0d3-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3e0d3-159">Windows Server 2019</span></span>
- <span data-ttu-id="3e0d3-160">Виртуальный рабочий стол Windows</span><span class="sxs-lookup"><span data-stu-id="3e0d3-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="3e0d3-161">Устройства в сети должны запускать одно из этих выпусков.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="3e0d3-162">Требования к оборудованию для Defender для конечной точки на устройствах одинаковы для поддерживаемых выпусков.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d3-163">Машины с мобильными версиями Windows (например, Windows CE и Windows 10 Mobile) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="3e0d3-164">Виртуальные Windows 10 Корпоративная 2016 с долгосрочным обслуживанием могут столкнуться с проблемой производительности при работе на платформах виртуализации, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="3e0d3-165">В виртуальных средах рекомендуется использовать Windows 10 Корпоративная LTSC 2019 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="3e0d3-166">Другие поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="3e0d3-166">Other supported operating systems</span></span>

- [<span data-ttu-id="3e0d3-167">Android</span><span class="sxs-lookup"><span data-stu-id="3e0d3-167">Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="3e0d3-168">iOS</span><span class="sxs-lookup"><span data-stu-id="3e0d3-168">iOS</span></span>](microsoft-defender-endpoint-ios.md)
- [<span data-ttu-id="3e0d3-169">Linux</span><span class="sxs-lookup"><span data-stu-id="3e0d3-169">Linux</span></span>](microsoft-defender-endpoint-linux.md)
- [<span data-ttu-id="3e0d3-170">macOS</span><span class="sxs-lookup"><span data-stu-id="3e0d3-170">macOS</span></span>](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> <span data-ttu-id="3e0d3-171">Для работы интеграции необходимо подтвердить, что дистрибутивы Linux и версии Android, iOS и macOS совместимы с Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-171">You'll need to confirm the Linux distributions and versions of Android, iOS, and macOS are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="3e0d3-172">Требования к сетевому хранению и хранению данных и конфигурации</span><span class="sxs-lookup"><span data-stu-id="3e0d3-172">Network and data storage and configuration requirements</span></span>

<span data-ttu-id="3e0d3-173">При первом запуске мастера бортовой связи необходимо выбрать, где хранятся данные Microsoft Defender для конечных точек: в Европейском союзе, Соединенном Королевстве или центрах обработки данных в США.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="3e0d3-174">Невозможно изменить расположение хранилища данных после первой установки.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="3e0d3-175">Дополнительные сведения о том, где и как Майкрософт хранит данные, просмотрите в [Microsoft Defender для](data-storage-privacy.md) хранения данных конечной точки и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="3e0d3-176">Параметры диагностических данных</span><span class="sxs-lookup"><span data-stu-id="3e0d3-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d3-177">Microsoft Defender для конечной точки не требует определенного уровня диагностики до тех пор, пока он включен.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="3e0d3-178">Убедитесь, что служба диагностических данных включена на всех устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="3e0d3-179">По умолчанию эта служба включена.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-179">By default, this service is enabled.</span></span> <span data-ttu-id="3e0d3-180">Это хорошая практика, чтобы проверить, чтобы убедиться, что вы получите данные датчика от них.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="3e0d3-181">**Используйте командную строку для проверки типа Windows 10 службы диагностических данных:**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="3e0d3-182">Откройте на устройстве повышенную командную строку:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="3e0d3-183">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="3e0d3-184">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="3e0d3-185">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="3e0d3-186">Если служба включена, результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Результат команды sc-запроса для diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="3e0d3-188">Необходимо настроить службу для автоматического запуска,  если START_TYPE не установлено AUTO_START **.**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="3e0d3-189">**Используйте командную строку, чтобы Windows 10 службу диагностических данных для автоматического запуска:**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="3e0d3-190">Откройте повышенную командную строку в конечной точке:</span><span class="sxs-lookup"><span data-stu-id="3e0d3-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="3e0d3-191">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="3e0d3-192">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="3e0d3-193">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="3e0d3-194">Отображается сообщение об успехе.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-194">A success message is displayed.</span></span> <span data-ttu-id="3e0d3-195">Проверьте изменение, введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="3e0d3-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="3e0d3-196">Подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-196">Internet connectivity</span></span>

<span data-ttu-id="3e0d3-197">Подключение к Интернету на устройствах требуется напрямую или через прокси.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="3e0d3-198">Датчик Defender для конечной точки может использовать среднюю пропускную способность 5 МБ для связи с облачной службой Defender для конечной точки и отчета о кибер-данных.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="3e0d3-199">Разовая деятельность, например загрузка файлов и коллекция пакетов расследований, не включаются в эту среднюю пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="3e0d3-200">Дополнительные сведения о дополнительных параметрах конфигурации прокси см. в перенастройке прокси-сервера устройства и параметров [подключения к Интернету.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="3e0d3-201">Перед устройством необходимо включить службу диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="3e0d3-202">Служба включена по умолчанию в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="3e0d3-203">антивирусная программа в Microsoft Defender конфигурации</span><span class="sxs-lookup"><span data-stu-id="3e0d3-203">Microsoft Defender Antivirus configuration requirement</span></span>

<span data-ttu-id="3e0d3-204">Агент Defender для конечной точки зависит от способности антивирусная программа в Microsoft Defender сканировать файлы и предоставлять сведения о них.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="3e0d3-205">Настройка обновлений для аналитики безопасности на устройствах Defender для конечных точек независимо антивирусная программа в Microsoft Defender является активным антивирусом или нет.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="3e0d3-206">Дополнительные сведения см. в [антивирусная программа в Microsoft Defender обновления и применение базовых показателей.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="3e0d3-207">Если антивирусная программа в Microsoft Defender не является активным антивирусным программным обеспечением в организации и используется служба Defender для конечных точек, антивирусная программа в Microsoft Defender переходит в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="3e0d3-208">Если организация отключается антивирусная программа в Microsoft Defender групповой политики или другими методами, устройства, которые находятся на борту, должны быть исключены из этой групповой политики.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="3e0d3-209">Если вы на бортовых серверах и антивирусная программа в Microsoft Defender не является активным антивирусным программным обеспечением на серверах, антивирусная программа в Microsoft Defender необходимо настроить, чтобы перейти в пассивный режим или отсеять.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="3e0d3-210">Конфигурация зависит от версии сервера.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="3e0d3-211">Дополнительные сведения см. [в антивирусная программа в Microsoft Defender совместимости.](/security/defender-endpoint/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-211">For more information, see [Microsoft Defender Antivirus compatibility](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d3-212">Обычная политика группы не применяется к tamper Protection, и изменения антивирусная программа в Microsoft Defender параметров будут игнорироваться при виостановке защиты от тамперов.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="3e0d3-213">антивирусная программа в Microsoft Defender Включен драйвер раннего запуска антивирусных программ (ELAM)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>

<span data-ttu-id="3e0d3-214">Если вы работаете антивирусная программа в Microsoft Defender в качестве основного антивирусного продукта на устройствах, агент Defender для конечных точек успешно будет на борту.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="3e0d3-215">Если вы работаете с сторонним клиентом противомалярийных программ и используете решения для управления мобильными устройствами или Microsoft Endpoint Manager (текущая ветвь), необходимо убедиться, что антивирусная программа в Microsoft Defender драйвер ELAM включен.</span><span class="sxs-lookup"><span data-stu-id="3e0d3-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="3e0d3-216">Дополнительные сведения см. в антивирусная программа в Microsoft Defender, чтобы политика не [отключалась.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="3e0d3-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="3e0d3-217">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3e0d3-217">Related topics</span></span>

- [<span data-ttu-id="3e0d3-218">Настройка microsoft Defender для развертывания конечных точек</span><span class="sxs-lookup"><span data-stu-id="3e0d3-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="3e0d3-219">Подключение устройств</span><span class="sxs-lookup"><span data-stu-id="3e0d3-219">Onboard devices</span></span>](onboard-configure.md)
