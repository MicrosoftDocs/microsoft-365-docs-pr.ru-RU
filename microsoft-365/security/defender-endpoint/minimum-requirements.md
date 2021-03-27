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
ms.openlocfilehash: 6a8e1091490cb9f3fe1eedadec0b76a56ada936e
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379494"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="d5d95-104">Минимальные требования к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d5d95-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5d95-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d5d95-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5d95-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d5d95-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d5d95-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5d95-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d5d95-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d5d95-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5d95-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d5d95-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="d5d95-110">Для бортовых устройств к службе существует несколько минимальных требований.</span><span class="sxs-lookup"><span data-stu-id="d5d95-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="d5d95-111">Узнайте о требованиях к лицензированию, оборудованию и программному обеспечению и других параметрах конфигурации для бортовых устройств службы.</span><span class="sxs-lookup"><span data-stu-id="d5d95-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="d5d95-112">Узнайте о последних усовершенствованиях в сообществе Защитник для конечной точки: [Защитник для конечной точки.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)</span><span class="sxs-lookup"><span data-stu-id="d5d95-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="d5d95-113">Defender for Endpoint в недавней оценке MITRE продемонстрировал ведущие в отрасли возможности оптики и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d5d95-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="d5d95-114">Read: [Insights from the MITRE ATT&CK-based assessment](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="d5d95-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d5d95-115">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="d5d95-115">Licensing requirements</span></span>
<span data-ttu-id="d5d95-116">Microsoft Defender для конечной точки требует одно из следующих предложений по лицензированию томов Корпорации Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="d5d95-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="d5d95-117">Windows 10 Корпоративная E5</span><span class="sxs-lookup"><span data-stu-id="d5d95-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="d5d95-118">Windows 10 для образовательных учреждений A5</span><span class="sxs-lookup"><span data-stu-id="d5d95-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="d5d95-119">Microsoft 365 E5 (M365 E5), которая включает Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="d5d95-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="d5d95-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="d5d95-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="d5d95-121">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d5d95-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="d5d95-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="d5d95-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="d5d95-123">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d5d95-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-124">Лицензированные пользователи могут использовать Microsoft Defender для конечной точки на пяти одновременном устройстве.</span><span class="sxs-lookup"><span data-stu-id="d5d95-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="d5d95-125">Microsoft Defender для конечной точки также доступен для покупки у поставщика облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="d5d95-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="d5d95-126">Microsoft Defender для конечной точки для серверов требует одного из следующих вариантов лицензирования:</span><span class="sxs-lookup"><span data-stu-id="d5d95-126">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="d5d95-127">Центр безопасности Azure с включенной службой Защитник Azure</span><span class="sxs-lookup"><span data-stu-id="d5d95-127">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="d5d95-128">Microsoft Defender для конечной точки для сервера (по одной на закрытый сервер)</span><span class="sxs-lookup"><span data-stu-id="d5d95-128">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-129">Клиенты могут приобретать лицензии на серверы (по одной на крытую среду операционной системы сервера)для Microsoft Defender для конечной точки для серверов, если у них есть совокупный минимум 50 лицензий для одной или более из следующих лицензий пользователей:</span><span class="sxs-lookup"><span data-stu-id="d5d95-129">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="d5d95-130">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d5d95-130">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="d5d95-131">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="d5d95-131">Windows E5/A5</span></span>
> * <span data-ttu-id="d5d95-132">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="d5d95-132">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="d5d95-133">Безопасность Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="d5d95-133">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="d5d95-134">Подробные сведения о лицензировании см. на [сайте Условия](https://www.microsoft.com/licensing/terms/) продукта и поработать с командой учетных записей, чтобы узнать больше об условиях и условиях.</span><span class="sxs-lookup"><span data-stu-id="d5d95-134">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="d5d95-135">Дополнительные сведения о массиве функций в выпусках Windows 10 см. в выпуске [Compare Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="d5d95-135">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="d5d95-136">Подробную таблицу сравнения сравнения коммерческих выпусков Windows 10 см. в сопоставлении [PDF.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="d5d95-136">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="d5d95-137">Требования к браузеру</span><span class="sxs-lookup"><span data-stu-id="d5d95-137">Browser requirements</span></span>
<span data-ttu-id="d5d95-138">Доступ к Защитнику для конечной точки делается через браузер, поддерживая следующие браузеры:</span><span class="sxs-lookup"><span data-stu-id="d5d95-138">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="d5d95-139">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d5d95-139">Microsoft Edge</span></span>
- <span data-ttu-id="d5d95-140">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="d5d95-140">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-141">Хотя другие браузеры могут работать, указанные браузеры поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d5d95-141">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="d5d95-142">Требования к оборудованию и программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="d5d95-142">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="d5d95-143">Поддерживаемые версии Windows</span><span class="sxs-lookup"><span data-stu-id="d5d95-143">Supported Windows versions</span></span>
- <span data-ttu-id="d5d95-144">Windows 7 SP1 Enterprise[(требуется ESU для поддержки.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="d5d95-144">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="d5d95-145">Windows 7 SP1 Pro[(требуется ESU для поддержки.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="d5d95-145">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="d5d95-146">Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="d5d95-146">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="d5d95-147">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="d5d95-147">Windows 8.1 Pro</span></span>
- <span data-ttu-id="d5d95-148">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="d5d95-148">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="d5d95-149">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="d5d95-149">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="d5d95-150">Windows 10 для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="d5d95-150">Windows 10 Education</span></span>
- <span data-ttu-id="d5d95-151">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="d5d95-151">Windows 10 Pro</span></span>
- <span data-ttu-id="d5d95-152">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="d5d95-152">Windows 10 Pro Education</span></span>
- <span data-ttu-id="d5d95-153">Сервер Windows</span><span class="sxs-lookup"><span data-stu-id="d5d95-153">Windows server</span></span>
  - <span data-ttu-id="d5d95-154">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="d5d95-154">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="d5d95-155">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d5d95-155">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="d5d95-156">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d5d95-156">Windows Server 2016</span></span>
  - <span data-ttu-id="d5d95-157">Windows Server, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d5d95-157">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="d5d95-158">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d5d95-158">Windows Server 2019</span></span>
- <span data-ttu-id="d5d95-159">Виртуальный рабочий стол Windows</span><span class="sxs-lookup"><span data-stu-id="d5d95-159">Windows Virtual Desktop</span></span>

<span data-ttu-id="d5d95-160">Устройства в сети должны запускать одно из этих выпусков.</span><span class="sxs-lookup"><span data-stu-id="d5d95-160">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="d5d95-161">Требования к оборудованию для Defender для конечной точки на устройствах одинаковы для поддерживаемых выпусков.</span><span class="sxs-lookup"><span data-stu-id="d5d95-161">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-162">Машины с мобильными версиями Windows (например, Windows CE Windows 10 Mobile) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d5d95-162">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="d5d95-163">Виртуальные машины под управлением Windows 10 Enterprise 2016 LTSB могут столкнуться с проблемой производительности при работе на платформах виртуализации, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5d95-163">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="d5d95-164">В виртуальных средах рекомендуется использовать Windows 10 Enterprise LTSC 2019 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d5d95-164">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="d5d95-165">Другие поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="d5d95-165">Other supported operating systems</span></span>
- <span data-ttu-id="d5d95-166">Android</span><span class="sxs-lookup"><span data-stu-id="d5d95-166">Android</span></span>
- <span data-ttu-id="d5d95-167">iOS</span><span class="sxs-lookup"><span data-stu-id="d5d95-167">iOS</span></span>
- <span data-ttu-id="d5d95-168">Linux</span><span class="sxs-lookup"><span data-stu-id="d5d95-168">Linux</span></span>
- <span data-ttu-id="d5d95-169">macOS</span><span class="sxs-lookup"><span data-stu-id="d5d95-169">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-170">Вам потребуется подтвердить дистрибутивы Linux и версии Android, iOS и macOS, совместимые с Defender для конечной точки для работы интеграции.</span><span class="sxs-lookup"><span data-stu-id="d5d95-170">You'll need to confirm the Linux distributions and versions of Android, iOS and macOS you've are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="d5d95-171">Требования к сетевому хранению и хранению данных и конфигурации</span><span class="sxs-lookup"><span data-stu-id="d5d95-171">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="d5d95-172">При первом запуске мастера бортовой связи необходимо выбрать, где хранятся данные Microsoft Defender для конечных точек: в Европейском союзе, Соединенном Королевстве или центрах обработки данных в США.</span><span class="sxs-lookup"><span data-stu-id="d5d95-172">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="d5d95-173">Невозможно изменить расположение хранилища данных после первой установки.</span><span class="sxs-lookup"><span data-stu-id="d5d95-173">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="d5d95-174">Дополнительные сведения о том, где и как Майкрософт хранит данные, просмотрите в [Microsoft Defender для](data-storage-privacy.md) хранения данных конечной точки и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="d5d95-174">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="d5d95-175">Параметры диагностических данных</span><span class="sxs-lookup"><span data-stu-id="d5d95-175">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-176">Microsoft Defender для конечной точки не требует определенного уровня диагностики до тех пор, пока он включен.</span><span class="sxs-lookup"><span data-stu-id="d5d95-176">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="d5d95-177">Убедитесь, что служба диагностических данных включена на всех устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="d5d95-177">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="d5d95-178">По умолчанию эта служба включена.</span><span class="sxs-lookup"><span data-stu-id="d5d95-178">By default, this service is enabled.</span></span> <span data-ttu-id="d5d95-179">Это хорошая практика, чтобы проверить, чтобы убедиться, что вы получите данные датчика от них.</span><span class="sxs-lookup"><span data-stu-id="d5d95-179">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="d5d95-180">**Используйте командную строку, чтобы проверить тип** запуска службы диагностических данных Windows 10:</span><span class="sxs-lookup"><span data-stu-id="d5d95-180">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="d5d95-181">Откройте на устройстве повышенную командную строку:</span><span class="sxs-lookup"><span data-stu-id="d5d95-181">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="d5d95-182">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d5d95-182">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="d5d95-183">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="d5d95-183">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="d5d95-184">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="d5d95-184">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="d5d95-185">Если служба включена, результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d5d95-185">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Результат команды sc-запроса для diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="d5d95-187">Необходимо настроить службу для автоматического запуска,  если START_TYPE не установлено AUTO_START **.**</span><span class="sxs-lookup"><span data-stu-id="d5d95-187">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="d5d95-188">**Чтобы автоматически запустить службу диагностических данных Windows 10, используйте командную строку:**</span><span class="sxs-lookup"><span data-stu-id="d5d95-188">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="d5d95-189">Откройте повышенную командную строку в конечной точке:</span><span class="sxs-lookup"><span data-stu-id="d5d95-189">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="d5d95-190">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d5d95-190">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="d5d95-191">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="d5d95-191">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="d5d95-192">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="d5d95-192">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="d5d95-193">Отображается сообщение об успехе.</span><span class="sxs-lookup"><span data-stu-id="d5d95-193">A success message is displayed.</span></span> <span data-ttu-id="d5d95-194">Проверьте изменение, введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="d5d95-194">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="d5d95-195">Подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="d5d95-195">Internet connectivity</span></span>
<span data-ttu-id="d5d95-196">Подключение к Интернету на устройствах требуется напрямую или через прокси.</span><span class="sxs-lookup"><span data-stu-id="d5d95-196">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="d5d95-197">Датчик Defender для конечной точки может использовать среднюю пропускную способность 5 МБ для связи с облачной службой Defender для конечной точки и отчета о кибер-данных.</span><span class="sxs-lookup"><span data-stu-id="d5d95-197">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="d5d95-198">Разовая деятельность, например загрузка файлов и коллекция пакетов расследований, не включаются в эту среднюю пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="d5d95-198">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="d5d95-199">Дополнительные сведения о дополнительных параметрах конфигурации прокси см. в перенастройке прокси-сервера устройства и параметров [подключения к Интернету.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="d5d95-199">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="d5d95-200">Перед устройством необходимо включить службу диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="d5d95-200">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="d5d95-201">Служба включена по умолчанию в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d5d95-201">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="d5d95-202">Требование конфигурации антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d5d95-202">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="d5d95-203">Агент Defender для конечной точки зависит от способности антивируса Microsoft Defender сканировать файлы и предоставлять сведения о них.</span><span class="sxs-lookup"><span data-stu-id="d5d95-203">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="d5d95-204">Настройте обновления аналитики безопасности на устройствах Defender для конечных точек независимо от того, является ли антивирус Microsoft Defender активным антивирусом или нет.</span><span class="sxs-lookup"><span data-stu-id="d5d95-204">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="d5d95-205">Дополнительные сведения см. в [веб-сайте Управление обновлениями антивирусного](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)антивируса Microsoft Defender и применение базовых данных.</span><span class="sxs-lookup"><span data-stu-id="d5d95-205">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="d5d95-206">Если антивирус Microsoft Defender не является активным антивирусом в организации и вы используете службу Defender для конечных точек, антивирус Microsoft Defender переходит в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="d5d95-206">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="d5d95-207">Если ваша организация отключил антивирус Microsoft Defender с помощью групповой политики или других методов, устройства, которые находятся на борту, должны быть исключены из этой групповой политики.</span><span class="sxs-lookup"><span data-stu-id="d5d95-207">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="d5d95-208">Если вы на бортовых серверах, а антивирус Microsoft Defender не является активным антивирусным обеспечением на серверах, антивирус Microsoft Defender необходимо настроить, чтобы перейти в пассивный режим или отсеять.</span><span class="sxs-lookup"><span data-stu-id="d5d95-208">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="d5d95-209">Конфигурация зависит от версии сервера.</span><span class="sxs-lookup"><span data-stu-id="d5d95-209">The configuration is dependent on the server version.</span></span> <span data-ttu-id="d5d95-210">Дополнительные сведения см. в [веб-сайте Совместимость антивирусных программ Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d5d95-210">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d5d95-211">Обычная политика группы не применяется к защите от тамперов, и изменения параметров антивируса Microsoft Defender будут игнорироваться при внесения в нее защиты.</span><span class="sxs-lookup"><span data-stu-id="d5d95-211">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="d5d95-212">Включен драйвер антивируса Microsoft Defender Early Launch Antimalware (ELAM)</span><span class="sxs-lookup"><span data-stu-id="d5d95-212">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="d5d95-213">Если антивирус Microsoft Defender запущен в качестве основного антивирусного продукта на устройствах, агент Defender для конечных точек успешно будет на борту.</span><span class="sxs-lookup"><span data-stu-id="d5d95-213">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="d5d95-214">Если вы работаете с сторонним клиентом антивирусных программ и используете решения для управления мобильными устройствами или Microsoft Endpoint Manager (текущая ветвь), необходимо убедиться, что драйвер ELAM антивируса Microsoft Defender включен.</span><span class="sxs-lookup"><span data-stu-id="d5d95-214">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="d5d95-215">Дополнительные сведения см. в [веб-сайте Убедитесь,](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)что антивирус Microsoft Defender не отключен политикой.</span><span class="sxs-lookup"><span data-stu-id="d5d95-215">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="d5d95-216">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d5d95-216">Related topics</span></span>
- [<span data-ttu-id="d5d95-217">Настройка microsoft Defender для развертывания конечных точек</span><span class="sxs-lookup"><span data-stu-id="d5d95-217">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="d5d95-218">Бортовых устройств</span><span class="sxs-lookup"><span data-stu-id="d5d95-218">Onboard devices</span></span>](onboard-configure.md)
