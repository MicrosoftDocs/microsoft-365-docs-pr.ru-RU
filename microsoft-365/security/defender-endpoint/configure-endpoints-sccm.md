---
title: Подключение устройств Windows 10 с помощью Configuration Manager
description: Используйте Диспетчер конфигурации для развертывания пакета конфигурации на устройствах, чтобы устройства были размещены в службе.
keywords: бортовые устройства с помощью sccm, управления устройствами, настройка Microsoft Defender для устройств endpoint
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: d7c319e37fb804ee4dac3b6bff402942bbc2fa79
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339662"
---
# <a name="onboard-the-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="3c71a-104">На борту Windows 10 с помощью диспетчера конфигурации</span><span class="sxs-lookup"><span data-stu-id="3c71a-104">Onboard the Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c71a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3c71a-105">**Applies to:**</span></span>

- [<span data-ttu-id="3c71a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c71a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c71a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c71a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="3c71a-108">Microsoft Endpoint Configuration Manager текущего филиала</span><span class="sxs-lookup"><span data-stu-id="3c71a-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="3c71a-109">Диспетчер конфигураций System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3c71a-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="3c71a-110">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="3c71a-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3c71a-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="3c71a-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="3c71a-112">Поддерживаемые клиентские операционные системы</span><span class="sxs-lookup"><span data-stu-id="3c71a-112">Supported client operating systems</span></span>

<span data-ttu-id="3c71a-113">На основе версии диспетчера конфигурации можно использовать следующие клиентские операционные системы:</span><span class="sxs-lookup"><span data-stu-id="3c71a-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="3c71a-114">Configuration Manager version 1910 and prior</span><span class="sxs-lookup"><span data-stu-id="3c71a-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="3c71a-115">Компьютеры клиентов, работающие Windows 10</span><span class="sxs-lookup"><span data-stu-id="3c71a-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="3c71a-116">Configuration Manager version 2002 and later</span><span class="sxs-lookup"><span data-stu-id="3c71a-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="3c71a-117">Начиная с версии Configuration Manager 2002, вы можете использовать следующие операционные системы:</span><span class="sxs-lookup"><span data-stu-id="3c71a-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="3c71a-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3c71a-118">Windows 8.1</span></span>
- <span data-ttu-id="3c71a-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3c71a-119">Windows 10</span></span>
- <span data-ttu-id="3c71a-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3c71a-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="3c71a-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3c71a-121">Windows Server 2016</span></span>
- <span data-ttu-id="3c71a-122">Windows Server 2016 версии 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="3c71a-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="3c71a-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3c71a-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="3c71a-124">Дополнительные сведения о том, как Windows Server 2012 R2, Windows Server 2016 и Windows Server 2019, см. в Windows [серверов.](configure-server-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3c71a-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="3c71a-125">Бортовых устройств с System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3c71a-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="3c71a-126">[![Изображение PDF, показывающая различные пути развертывания](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3c71a-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="3c71a-127">Ознакомьтесь с [pdf или Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) чтобы узнать о различных путях развертывания Microsoft Defender для конечной точки. [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="3c71a-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="3c71a-128">Откройте пакет конфигурации Configuration Manager .zip файл *(WindowsDefenderATPOnboardingPackage.zip), загруженный* из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="3c71a-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="3c71a-129">Вы также можете получить пакет с [Microsoft 365 Defender портала:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3c71a-129">You can also get the package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="3c71a-130">В области навигации выберите **Параметры** управление устройствами конечных  >    >    >  **точек.**</span><span class="sxs-lookup"><span data-stu-id="3c71a-130">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="3c71a-131">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3c71a-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="3c71a-132">В поле **Метод развертывания** выберите System Center Configuration Manager **2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="3c71a-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="3c71a-133">Выберите **пакет Загрузка** и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="3c71a-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="3c71a-134">Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="3c71a-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="3c71a-135">У вас должен быть файл с именем *WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="3c71a-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="3c71a-136">Развертывание пакета, следуя шагам в статье [Packages and Programs System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="3c71a-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="3c71a-137">а.</span><span class="sxs-lookup"><span data-stu-id="3c71a-137">a.</span></span> <span data-ttu-id="3c71a-138">Выберите предопределяемую коллекцию устройств для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="3c71a-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="3c71a-139">Защитник для конечной точки не поддерживает вовне на этапе [Out-Of-Box Experience (OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="3c71a-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="3c71a-140">Убедитесь, что пользователи заполняют OOBE после Windows установки или обновления.</span><span class="sxs-lookup"><span data-stu-id="3c71a-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="3c71a-141">После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу.</span><span class="sxs-lookup"><span data-stu-id="3c71a-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="3c71a-142">Дополнительные сведения см. в таблице [Run a detection test on a newly onboarded Defender for Endpoint device.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="3c71a-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="3c71a-143">Обратите внимание, что в приложении Configuration Manager можно создать правило обнаружения, чтобы постоянно проверять, было ли устройство на борту.</span><span class="sxs-lookup"><span data-stu-id="3c71a-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="3c71a-144">Приложение — это другой тип объекта, чем пакет и программа.</span><span class="sxs-lookup"><span data-stu-id="3c71a-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="3c71a-145">Если устройство еще не установлено (в связи с завершением OOBE или по какой-либо другой причине), диспетчер конфигурации будет повторно фиксироваться на борту устройства до тех пор, пока правило не обнаружит изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="3c71a-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="3c71a-146">Это поведение может быть выполнено путем проверки правила обнаружения, если значение реестра "OnboardingState" (типа REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="3c71a-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="3c71a-147">Это значение реестра расположено в статье "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="3c71a-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="3c71a-148">Дополнительные сведения см. в [руб. В System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="3c71a-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="3c71a-149">Настройка параметров коллекции образцов</span><span class="sxs-lookup"><span data-stu-id="3c71a-149">Configure sample collection settings</span></span>

<span data-ttu-id="3c71a-150">Для каждого устройства можно установить значение конфигурации, чтобы определить, можно ли собирать образцы с устройства при Microsoft 365 Defender отправки файла для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="3c71a-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft 365 Defender to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="3c71a-151">Эти параметры конфигурации обычно делаются с помощью Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3c71a-151">These configuration settings are typically done through Configuration Manager.</span></span>

<span data-ttu-id="3c71a-152">Вы можете установить правило соответствия требованиям для элемента конфигурации в диспетчере конфигурации, чтобы изменить пример параметров обмена данными на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3c71a-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="3c71a-153">Это правило должно быть *элементом* настройки правил соответствия требованиям, который задает значение ключа реестра на целевых устройствах, чтобы убедиться, что они являются жалобами.</span><span class="sxs-lookup"><span data-stu-id="3c71a-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="3c71a-154">Конфигурация заданная с помощью следующей записи ключа реестра:</span><span class="sxs-lookup"><span data-stu-id="3c71a-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="3c71a-155">Где:</span><span class="sxs-lookup"><span data-stu-id="3c71a-155">Where:</span></span><br>
<span data-ttu-id="3c71a-156">Тип ключа — это D-WORD.</span><span class="sxs-lookup"><span data-stu-id="3c71a-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="3c71a-157">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="3c71a-157">Possible values are:</span></span>
- <span data-ttu-id="3c71a-158">0 — не разрешает общий доступ к примеру с этого устройства</span><span class="sxs-lookup"><span data-stu-id="3c71a-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="3c71a-159">1 — позволяет обмениваться всеми типами файлов с этого устройства</span><span class="sxs-lookup"><span data-stu-id="3c71a-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="3c71a-160">Значение по умолчанию в случае, если ключ реестра не существует, составляет 1.</span><span class="sxs-lookup"><span data-stu-id="3c71a-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="3c71a-161">Дополнительные сведения о соблюдении System Center Configuration Manager см. в введении параметров соответствия требованиям [в System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="3c71a-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="3c71a-162">Другие рекомендуемые параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="3c71a-162">Other recommended configuration settings</span></span>
<span data-ttu-id="3c71a-163">После включения устройств в службу важно воспользоваться включенными возможностями защиты от угроз, включив их в следующие рекомендуемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3c71a-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="3c71a-164">Конфигурация коллекции устройств</span><span class="sxs-lookup"><span data-stu-id="3c71a-164">Device collection configuration</span></span>
<span data-ttu-id="3c71a-165">Если используется диспетчер конфигурации конечной точки версии 2002 или более поздней версии, можно расширить развертывание, включив серверы или клиенты на более позднем уровне.</span><span class="sxs-lookup"><span data-stu-id="3c71a-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="3c71a-166">Конфигурация защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="3c71a-166">Next generation protection configuration</span></span>
<span data-ttu-id="3c71a-167">Рекомендуется использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="3c71a-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="3c71a-168">**Сканирование**</span><span class="sxs-lookup"><span data-stu-id="3c71a-168">**Scan**</span></span> <br>
- <span data-ttu-id="3c71a-169">Сканирование съемных устройств хранения, таких как USB-накопители: Да</span><span class="sxs-lookup"><span data-stu-id="3c71a-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="3c71a-170">**Защита в режиме реального времени**</span><span class="sxs-lookup"><span data-stu-id="3c71a-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="3c71a-171">Включить поведенческий мониторинг: Да</span><span class="sxs-lookup"><span data-stu-id="3c71a-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="3c71a-172">Включить защиту от потенциально нежелательных приложений при загрузке и до установки: Да</span><span class="sxs-lookup"><span data-stu-id="3c71a-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="3c71a-173">**Служба облачной защиты**</span><span class="sxs-lookup"><span data-stu-id="3c71a-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="3c71a-174">Тип членства в службе облачной защиты: расширенный членский состав</span><span class="sxs-lookup"><span data-stu-id="3c71a-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="3c71a-175">**Уменьшение поверхности атаки** Настройка всех доступных правил для аудита.</span><span class="sxs-lookup"><span data-stu-id="3c71a-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="3c71a-176">Блокировка этих действий может прервать законные бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="3c71a-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="3c71a-177">Оптимальный подход — настройка всех параметров аудита, определение безопасных для включения и включение параметров конечных точек, не обнаруживающих ложных срабатывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="3c71a-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="3c71a-178">**Защита сети**</span><span class="sxs-lookup"><span data-stu-id="3c71a-178">**Network protection**</span></span> <br>
<span data-ttu-id="3c71a-179">Перед включением сетевой защиты в режиме аудита или блокировки убедитесь, что вы установили обновление платформы антивирусных программ, которое можно получить на странице [поддержки.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="3c71a-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="3c71a-180">**Контролируемый доступ к папкам**</span><span class="sxs-lookup"><span data-stu-id="3c71a-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="3c71a-181">Включить функцию в режиме аудита не менее 30 дней.</span><span class="sxs-lookup"><span data-stu-id="3c71a-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="3c71a-182">После этого периода просмотрите обнаружения и создайте список приложений, которые могут записываться в защищенные каталоги.</span><span class="sxs-lookup"><span data-stu-id="3c71a-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="3c71a-183">Дополнительные сведения см. в [дополнительных сведениях о доступе к управляемым папкам.](evaluate-controlled-folder-access.md)</span><span class="sxs-lookup"><span data-stu-id="3c71a-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="3c71a-184">Offboard devices using Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3c71a-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="3c71a-185">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="3c71a-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="3c71a-186">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="3c71a-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="3c71a-187">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="3c71a-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="3c71a-188">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="3c71a-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="3c71a-189">Offboard devices using Microsoft Endpoint Manager current branch</span><span class="sxs-lookup"><span data-stu-id="3c71a-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="3c71a-190">Если вы используете Microsoft Endpoint Manager текущую ветвь, см. в статью Создание файла конфигурации [offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="3c71a-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="3c71a-191">Offboard devices using System Center R2 Configuration Manager 2012</span><span class="sxs-lookup"><span data-stu-id="3c71a-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="3c71a-192">Получите пакет offboarding с [Microsoft 365 Defender:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="3c71a-192">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="3c71a-193">В области навигации выберите отключение **Параметры** конечных  >  **точек** управления  >    >   **устройствами.**</span><span class="sxs-lookup"><span data-stu-id="3c71a-193">In the navigation pane, select **Settings** > **Endpoints** > **Device management** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="3c71a-194">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3c71a-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="3c71a-195">В поле **Метод развертывания** выберите System Center Configuration Manager **2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="3c71a-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="3c71a-196">Выберите **пакет Загрузка** и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="3c71a-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="3c71a-197">Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="3c71a-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="3c71a-198">У вас должен быть *файл с именем WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="3c71a-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="3c71a-199">Развертывание пакета, следуя шагам в статье [Packages and Programs System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="3c71a-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="3c71a-200">а.</span><span class="sxs-lookup"><span data-stu-id="3c71a-200">a.</span></span> <span data-ttu-id="3c71a-201">Выберите предопределяемую коллекцию устройств для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="3c71a-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c71a-202">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="3c71a-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="3c71a-203">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="3c71a-203">Monitor device configuration</span></span>

<span data-ttu-id="3c71a-204">Если вы используете текущую Microsoft Endpoint Manager, используйте встроенную панель мониторинга Defender для конечной точки в консоли Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3c71a-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="3c71a-205">Дополнительные сведения см. в [дополнительных сведениях Defender for Endpoint - Monitor.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="3c71a-205">For more information, see [Defender for Endpoint - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="3c71a-206">Если вы используете System Center 2012 R2 Configuration Manager, мониторинг состоит из двух частей:</span><span class="sxs-lookup"><span data-stu-id="3c71a-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="3c71a-207">Подтверждение правильного развертывания пакета конфигурации и успешного запуска (или успешного запуска) на устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="3c71a-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="3c71a-208">Проверка того, что устройства соответствуют службе Defender для конечной точки (это гарантирует, что устройство может завершить процесс бортовой обработки и может продолжать сообщать данные в службу).</span><span class="sxs-lookup"><span data-stu-id="3c71a-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="3c71a-209">Подтверждение правильного развертывания пакета конфигурации</span><span class="sxs-lookup"><span data-stu-id="3c71a-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="3c71a-210">В консоли Configuration Manager щелкните **Мониторинг** в нижней части панели навигации.</span><span class="sxs-lookup"><span data-stu-id="3c71a-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="3c71a-211">Выберите **Обзор** и **развертывание.**</span><span class="sxs-lookup"><span data-stu-id="3c71a-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="3c71a-212">Выберите развертывание с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="3c71a-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="3c71a-213">Просмотрите индикаторы состояния в **статье Статистика завершения** и состояние **контента.**</span><span class="sxs-lookup"><span data-stu-id="3c71a-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="3c71a-214">При сбойных развертываниях (устройствах с ошибками, невыполнением требований или сбойных состояниях) может потребоваться устранение неполадок устройств.</span><span class="sxs-lookup"><span data-stu-id="3c71a-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="3c71a-215">Дополнительные сведения см. в выпуске [Устранение неполадок в microsoft Defender для конечной](troubleshoot-onboarding.md)точки.</span><span class="sxs-lookup"><span data-stu-id="3c71a-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![Диспетчер конфигурации, показывающий успешное развертывание без ошибок](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="3c71a-217">Убедитесь, что устройства соответствуют службе Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="3c71a-217">Check that the devices are compliant with the Microsoft Defender for Endpoint service</span></span>

<span data-ttu-id="3c71a-218">Вы можете установить правило соответствия требованиям для элемента конфигурации System Center 2012 R2 Configuration Manager для мониторинга развертывания.</span><span class="sxs-lookup"><span data-stu-id="3c71a-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="3c71a-219">Это правило должно быть *элементом* конфигурации правил соответствия требованиям, который отслеживает значение ключа реестра на целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="3c71a-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="3c71a-220">Мониторинг следующей записи ключа реестра:</span><span class="sxs-lookup"><span data-stu-id="3c71a-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="3c71a-221">Дополнительные сведения см. в введении параметров соответствия требованиям [в System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="3c71a-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c71a-222">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3c71a-222">Related topics</span></span>
- [<span data-ttu-id="3c71a-223">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="3c71a-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="3c71a-224">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="3c71a-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="3c71a-225">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="3c71a-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="3c71a-226">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="3c71a-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="3c71a-227">Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="3c71a-227">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="3c71a-228">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="3c71a-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
