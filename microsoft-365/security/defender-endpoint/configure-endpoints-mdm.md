---
title: Подключение устройств Windows 10 с помощью средств управления мобильными устройствами
description: Используйте средства управления мобильными устройствами для развертывания пакета конфигурации на устройствах, чтобы устройства были размещены в службе.
keywords: бортовые устройства с использованием mdm, управления устройствами, на борту устройств Microsoft Defender для конечных точек, mdm
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f0a0a35d41d56abfcc7975c9e79ff7d537b72f40
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338581"
---
# <a name="onboard-the-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="38b7c-104">На борту Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="38b7c-104">Onboard the Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="38b7c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="38b7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="38b7c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="38b7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="38b7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38b7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="38b7c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="38b7c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="38b7c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="38b7c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="38b7c-110">Для настройки устройств можно использовать решения управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="38b7c-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="38b7c-111">Defender for Endpoint поддерживает MDM, OMA-URIs для создания политик для управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="38b7c-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="38b7c-112">Дополнительные сведения об использовании CSP Defender для конечных точек см. в [CSP WindowsAdvancedThreatProtection и](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) [DDF WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="38b7c-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="38b7c-113">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="38b7c-113">Before you begin</span></span>
<span data-ttu-id="38b7c-114">Если вы используете Microsoft Intune, необходимо зарегистрироваться на устройстве MDM.</span><span class="sxs-lookup"><span data-stu-id="38b7c-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="38b7c-115">В противном случае параметры не будут успешно применены.</span><span class="sxs-lookup"><span data-stu-id="38b7c-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="38b7c-116">Дополнительные сведения о включаемом MDM с помощью Microsoft Intune см. в [Microsoft Intune.](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="38b7c-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="38b7c-117">На борту устройств с Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="38b7c-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="38b7c-118">[![Изображение pdf-файлов, демонстрирующих встроенные устройства в Defender для конечной точки с помощью Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="38b7c-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="38b7c-119">Ознакомьтесь с [PDF или Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) чтобы увидеть различные пути развертывания Defender для конечной точки. [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="38b7c-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="38b7c-120">Следуйте инструкциям [из Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="38b7c-120">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="38b7c-121">Дополнительные сведения об использовании CSP Defender для конечных точек см. в [CSP WindowsAdvancedThreatProtection и](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) [DDF WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="38b7c-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="38b7c-122">Политика состояния здоровья для **бортовых устройств** использует свойства только для чтения и не может быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="38b7c-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="38b7c-123">Настройка частоты отчетов о диагностических данных доступна только для устройств Windows 10 версии 1703.</span><span class="sxs-lookup"><span data-stu-id="38b7c-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="38b7c-124">После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу.</span><span class="sxs-lookup"><span data-stu-id="38b7c-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="38b7c-125">Дополнительные сведения см. в таблице Выполнить тест обнаружения на недавно созданном [устройстве Microsoft Defender для конечных точек.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="38b7c-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="38b7c-126">Ознакомьтесь с [pdf или Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) чтобы узнать о различных путях развертывания Microsoft Defender для конечной точки. [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="38b7c-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="38b7c-127">Offboard и мониторинг устройств с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="38b7c-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="38b7c-128">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="38b7c-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="38b7c-129">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="38b7c-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="38b7c-130">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="38b7c-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="38b7c-131">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="38b7c-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="38b7c-132">Получите пакет offboarding с [Microsoft 365 Defender:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="38b7c-132">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

   1. <span data-ttu-id="38b7c-133">В области навигации выберите отключение **Параметры** конечных  >  **точек** управления  >    >  **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="38b7c-133">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Offboarding**.</span></span>

   1. <span data-ttu-id="38b7c-134">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="38b7c-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="38b7c-135">В поле **Метод развертывания** выберите **управление мобильными устройствами или Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="38b7c-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="38b7c-136">Щелкните **пакет Загрузка** и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="38b7c-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="38b7c-137">Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="38b7c-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="38b7c-138">Файл с именем *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding.*</span><span class="sxs-lookup"><span data-stu-id="38b7c-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="38b7c-139">Используйте настраиваемую Microsoft Intune настройки для развертывания следующих поддерживаемых ПАРАМЕТРОВ OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="38b7c-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="38b7c-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="38b7c-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="38b7c-141">Тип даты: String</span><span class="sxs-lookup"><span data-stu-id="38b7c-141">Date type: String</span></span><br/>
      <span data-ttu-id="38b7c-142">Значение. [Скопируйте и включите значение из содержимого файла WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="38b7c-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="38b7c-143">Дополнительные сведения о параметрах политики Microsoft Intune см. в Windows 10 параметров политики [в Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="38b7c-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="38b7c-144">Политика состояния здоровья для **отключенных** устройств использует свойства только для чтения и не может быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="38b7c-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38b7c-145">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="38b7c-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="38b7c-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="38b7c-146">Related topics</span></span>
- [<span data-ttu-id="38b7c-147">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="38b7c-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="38b7c-148">На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="38b7c-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="38b7c-149">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="38b7c-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="38b7c-150">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="38b7c-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="38b7c-151">Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="38b7c-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="38b7c-152">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="38b7c-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
