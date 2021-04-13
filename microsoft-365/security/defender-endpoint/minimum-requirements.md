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
ms.openlocfilehash: 330406b3540becafb0ffac8cbbc36437a2e57f60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688841"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="5ecca-104">Минимальные требования к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ecca-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ecca-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ecca-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ecca-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ecca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ecca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ecca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5ecca-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5ecca-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5ecca-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5ecca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="5ecca-110">Для бортовых устройств к службе существует несколько минимальных требований.</span><span class="sxs-lookup"><span data-stu-id="5ecca-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="5ecca-111">Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для бортовых устройств службы.</span><span class="sxs-lookup"><span data-stu-id="5ecca-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="5ecca-112">Узнайте о последних усовершенствованиях в сообществе Защитник для конечной точки: [Защитник для конечной точки.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)</span><span class="sxs-lookup"><span data-stu-id="5ecca-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="5ecca-113">Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="5ecca-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="5ecca-114">Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="5ecca-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5ecca-115">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="5ecca-115">Licensing requirements</span></span>
<span data-ttu-id="5ecca-116">Microsoft Defender для конечной точки требует одно из следующих предложений по лицензированию томов Корпорации Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="5ecca-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="5ecca-117">Windows 10 Корпоративная E5</span><span class="sxs-lookup"><span data-stu-id="5ecca-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="5ecca-118">Windows 10 для образовательных учреждений A5</span><span class="sxs-lookup"><span data-stu-id="5ecca-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="5ecca-119">Microsoft 365 E5 (M365 E5), которая включает Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="5ecca-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="5ecca-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="5ecca-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="5ecca-121">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5ecca-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="5ecca-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="5ecca-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="5ecca-123">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ecca-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="5ecca-124">Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.</span><span class="sxs-lookup"><span data-stu-id="5ecca-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="5ecca-125">Microsoft Defender для конечной точки также доступен для покупки у поставщика облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="5ecca-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="5ecca-126">Для VMs RDSH не требуется отдельная лицензия Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5ecca-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="5ecca-127">Microsoft Defender для конечной точки для серверов требует одного из следующих вариантов лицензирования:</span><span class="sxs-lookup"><span data-stu-id="5ecca-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="5ecca-128">Центр безопасности Azure с включенной службой Защитник Azure</span><span class="sxs-lookup"><span data-stu-id="5ecca-128">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="5ecca-129">Microsoft Defender для конечной точки для сервера (по одной на закрытый сервер)</span><span class="sxs-lookup"><span data-stu-id="5ecca-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="5ecca-130">Клиенты могут приобретать лицензии на серверы (по одной на крытую среду операционной системы сервера)для Microsoft Defender для конечной точки для серверов, если у них есть совокупный минимум 50 лицензий для одной или более из следующих лицензий пользователей:</span><span class="sxs-lookup"><span data-stu-id="5ecca-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="5ecca-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ecca-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="5ecca-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="5ecca-132">Windows E5/A5</span></span>
> * <span data-ttu-id="5ecca-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="5ecca-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="5ecca-134">Безопасность Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="5ecca-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="5ecca-135">Подробные сведения о лицензировании см. на [сайте Условия](https://www.microsoft.com/licensing/terms/) продукта и поработать с командой учетных записей, чтобы узнать больше об условиях и условиях.</span><span class="sxs-lookup"><span data-stu-id="5ecca-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="5ecca-136">Дополнительные сведения о массиве функций в выпусках Windows 10 см. в выпуске [Compare Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="5ecca-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="5ecca-137">Подробную таблицу сравнения сравнения коммерческих выпусков Windows 10 см. в сопоставлении [PDF.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="5ecca-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="5ecca-138">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="5ecca-138">Browser requirements</span></span>
<span data-ttu-id="5ecca-139">Доступ к Защитнику для конечной точки делается через браузер, поддерживая следующие браузеры:</span><span class="sxs-lookup"><span data-stu-id="5ecca-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="5ecca-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5ecca-140">Microsoft Edge</span></span>
- <span data-ttu-id="5ecca-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="5ecca-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="5ecca-142">Хотя другие браузеры могут работать, указанные браузеры поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5ecca-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="5ecca-143">Требования к оборудованию и программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="5ecca-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="5ecca-144">Поддерживаемые версии Windows</span><span class="sxs-lookup"><span data-stu-id="5ecca-144">Supported Windows versions</span></span>
- <span data-ttu-id="5ecca-145">Windows 7 SP1 Enterprise[(требуется ESU для поддержки.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="5ecca-145">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="5ecca-146">Windows 7 SP1 Pro[(требуется ESU для поддержки.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="5ecca-146">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="5ecca-147">Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="5ecca-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="5ecca-148">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="5ecca-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="5ecca-149">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="5ecca-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="5ecca-150">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="5ecca-150">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="5ecca-151">Windows 10 для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="5ecca-151">Windows 10 Education</span></span>
- <span data-ttu-id="5ecca-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="5ecca-152">Windows 10 Pro</span></span>
- <span data-ttu-id="5ecca-153">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="5ecca-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="5ecca-154">Сервер Windows</span><span class="sxs-lookup"><span data-stu-id="5ecca-154">Windows server</span></span>
  - <span data-ttu-id="5ecca-155">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="5ecca-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="5ecca-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5ecca-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="5ecca-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5ecca-157">Windows Server 2016</span></span>
  - <span data-ttu-id="5ecca-158">Windows Server, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="5ecca-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="5ecca-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="5ecca-159">Windows Server 2019</span></span>
- <span data-ttu-id="5ecca-160">Виртуальный рабочий стол Windows</span><span class="sxs-lookup"><span data-stu-id="5ecca-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="5ecca-161">Устройства в сети должны запускать одно из этих выпусков.</span><span class="sxs-lookup"><span data-stu-id="5ecca-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="5ecca-162">Требования к оборудованию для Defender для конечной точки на устройствах одинаковы для поддерживаемых выпусков.</span><span class="sxs-lookup"><span data-stu-id="5ecca-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="5ecca-163">Машины с мобильными версиями Windows (например, Windows CE Windows 10 Mobile) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5ecca-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="5ecca-164">Виртуальные машины под управлением Windows 10 Enterprise 2016 LTSB могут столкнуться с проблемой производительности при работе на платформах виртуализации, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ecca-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="5ecca-165">В виртуальных средах рекомендуется использовать Windows 10 Enterprise LTSC 2019 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5ecca-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="5ecca-166">Другие поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="5ecca-166">Other supported operating systems</span></span>
- [<span data-ttu-id="5ecca-167">Android</span><span class="sxs-lookup"><span data-stu-id="5ecca-167">Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="5ecca-168">iOS</span><span class="sxs-lookup"><span data-stu-id="5ecca-168">iOS</span></span>](microsoft-defender-endpoint-ios.md)
- [<span data-ttu-id="5ecca-169">Linux</span><span class="sxs-lookup"><span data-stu-id="5ecca-169">Linux</span></span>](microsoft-defender-endpoint-linux.md)
- [<span data-ttu-id="5ecca-170">macOS</span><span class="sxs-lookup"><span data-stu-id="5ecca-170">macOS</span></span>](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> <span data-ttu-id="5ecca-171">Вам потребуется подтвердить дистрибутивы Linux и версии Android, iOS и macOS, совместимые с Defender для конечной точки для работы интеграции.</span><span class="sxs-lookup"><span data-stu-id="5ecca-171">You'll need to confirm the Linux distributions and versions of Android, iOS and macOS you've are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="5ecca-172">Требования к сетевому хранению и хранению данных и конфигурации</span><span class="sxs-lookup"><span data-stu-id="5ecca-172">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="5ecca-173">При первом запуске мастера бортовой связи необходимо выбрать, где хранятся данные Microsoft Defender для конечных точек: в Европейском союзе, Соединенном Королевстве или центрах обработки данных в США.</span><span class="sxs-lookup"><span data-stu-id="5ecca-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="5ecca-174">Невозможно изменить расположение хранилища данных после первой установки.</span><span class="sxs-lookup"><span data-stu-id="5ecca-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="5ecca-175">Дополнительные сведения о том, где и как Майкрософт хранит данные, просмотрите в [Microsoft Defender для](data-storage-privacy.md) хранения данных конечной точки и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="5ecca-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="5ecca-176">Параметры диагностических данных</span><span class="sxs-lookup"><span data-stu-id="5ecca-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="5ecca-177">Microsoft Defender для конечной точки не требует определенного уровня диагностики до тех пор, пока он включен.</span><span class="sxs-lookup"><span data-stu-id="5ecca-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="5ecca-178">Убедитесь, что служба диагностических данных включена на всех устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="5ecca-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="5ecca-179">По умолчанию эта служба включена.</span><span class="sxs-lookup"><span data-stu-id="5ecca-179">By default, this service is enabled.</span></span> <span data-ttu-id="5ecca-180">Это хорошая практика, чтобы проверить, чтобы убедиться, что вы получите данные датчика от них.</span><span class="sxs-lookup"><span data-stu-id="5ecca-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="5ecca-181">**Используйте командную строку, чтобы проверить тип** запуска службы диагностических данных Windows 10:</span><span class="sxs-lookup"><span data-stu-id="5ecca-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="5ecca-182">Откройте на устройстве повышенную командную строку:</span><span class="sxs-lookup"><span data-stu-id="5ecca-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="5ecca-183">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5ecca-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="5ecca-184">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="5ecca-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="5ecca-185">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="5ecca-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="5ecca-186">Если служба включена, результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5ecca-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Результат команды sc-запроса для diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="5ecca-188">Необходимо настроить службу для автоматического запуска,  если START_TYPE не установлено AUTO_START **.**</span><span class="sxs-lookup"><span data-stu-id="5ecca-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="5ecca-189">**Чтобы автоматически запустить службу диагностических данных Windows 10, используйте командную строку:**</span><span class="sxs-lookup"><span data-stu-id="5ecca-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="5ecca-190">Откройте повышенную командную строку в конечной точке:</span><span class="sxs-lookup"><span data-stu-id="5ecca-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="5ecca-191">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5ecca-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="5ecca-192">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="5ecca-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="5ecca-193">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="5ecca-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="5ecca-194">Отображается сообщение об успехе.</span><span class="sxs-lookup"><span data-stu-id="5ecca-194">A success message is displayed.</span></span> <span data-ttu-id="5ecca-195">Проверьте изменение, введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="5ecca-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="5ecca-196">Подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="5ecca-196">Internet connectivity</span></span>
<span data-ttu-id="5ecca-197">Подключение к Интернету на устройствах требуется напрямую или через прокси.</span><span class="sxs-lookup"><span data-stu-id="5ecca-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="5ecca-198">Датчик Defender для конечной точки может использовать среднюю пропускную способность 5 МБ для связи с облачной службой Defender для конечной точки и отчета о кибер-данных.</span><span class="sxs-lookup"><span data-stu-id="5ecca-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="5ecca-199">Разовая деятельность, например загрузка файлов и коллекция пакетов расследований, не включаются в эту среднюю пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="5ecca-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="5ecca-200">Дополнительные сведения о дополнительных параметрах конфигурации прокси см. в перенастройке прокси-сервера устройства и параметров [подключения к Интернету.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="5ecca-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="5ecca-201">Перед устройством необходимо включить службу диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="5ecca-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="5ecca-202">Служба включена по умолчанию в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5ecca-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="5ecca-203">Требование конфигурации антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5ecca-203">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="5ecca-204">Агент Defender для конечной точки зависит от способности антивируса Microsoft Defender сканировать файлы и предоставлять сведения о них.</span><span class="sxs-lookup"><span data-stu-id="5ecca-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="5ecca-205">Настройте обновления аналитики безопасности на устройствах Defender для конечных точек независимо от того, является ли антивирус Microsoft Defender активным антивирусом или нет.</span><span class="sxs-lookup"><span data-stu-id="5ecca-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="5ecca-206">Дополнительные сведения см. в [веб-сайте Управление обновлениями антивирусного](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)антивируса Microsoft Defender и применение базовых данных.</span><span class="sxs-lookup"><span data-stu-id="5ecca-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="5ecca-207">Если антивирус Microsoft Defender не является активным антивирусом в организации и вы используете службу Defender для конечных точек, антивирус Microsoft Defender переходит в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="5ecca-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="5ecca-208">Если ваша организация отключил антивирус Microsoft Defender с помощью групповой политики или других методов, устройства, которые находятся на борту, должны быть исключены из этой групповой политики.</span><span class="sxs-lookup"><span data-stu-id="5ecca-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="5ecca-209">Если вы на бортовых серверах, а антивирус Microsoft Defender не является активным антивирусным обеспечением на серверах, антивирус Microsoft Defender необходимо настроить, чтобы перейти в пассивный режим или отсеять.</span><span class="sxs-lookup"><span data-stu-id="5ecca-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="5ecca-210">Конфигурация зависит от версии сервера.</span><span class="sxs-lookup"><span data-stu-id="5ecca-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="5ecca-211">Дополнительные сведения см. в [веб-сайте Совместимость антивирусных программ Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5ecca-211">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5ecca-212">Обычная политика группы не применяется к защите от тамперов, и изменения параметров антивируса Microsoft Defender будут игнорироваться при внесения в нее защиты.</span><span class="sxs-lookup"><span data-stu-id="5ecca-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="5ecca-213">Включен драйвер антивируса Microsoft Defender Early Launch Antimalware (ELAM)</span><span class="sxs-lookup"><span data-stu-id="5ecca-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="5ecca-214">Если антивирус Microsoft Defender запущен в качестве основного антивирусного продукта на устройствах, агент Defender для конечных точек успешно будет на борту.</span><span class="sxs-lookup"><span data-stu-id="5ecca-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="5ecca-215">Если вы работаете с сторонним клиентом антивирусных программ и используете решения для управления мобильными устройствами или Microsoft Endpoint Manager (текущая ветвь), необходимо убедиться, что драйвер ELAM антивируса Microsoft Defender включен.</span><span class="sxs-lookup"><span data-stu-id="5ecca-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="5ecca-216">Дополнительные сведения см. в [веб-сайте Убедитесь,](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)что антивирус Microsoft Defender не отключен политикой.</span><span class="sxs-lookup"><span data-stu-id="5ecca-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="5ecca-217">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5ecca-217">Related topics</span></span>
- [<span data-ttu-id="5ecca-218">Настройка microsoft Defender для развертывания конечных точек</span><span class="sxs-lookup"><span data-stu-id="5ecca-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="5ecca-219">Бортовых устройств</span><span class="sxs-lookup"><span data-stu-id="5ecca-219">Onboard devices</span></span>](onboard-configure.md)
