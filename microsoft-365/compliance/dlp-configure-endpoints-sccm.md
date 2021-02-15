---
title: Подключение устройств Windows 10 с помощью Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Используйте Configuration Manager для развертывания пакета конфигурации на устройствах, чтобы они были вовсю в службе.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769475"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="aad0d-103">Подключение устройств Windows 10 с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aad0d-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="aad0d-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="aad0d-104">**Applies to:**</span></span>

- [<span data-ttu-id="aad0d-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="aad0d-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="aad0d-106">Диспетчер конфигураций System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="aad0d-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="aad0d-107">Ветвь устройств с помощью System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aad0d-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="aad0d-108">Откройте ZIP-файл пакета конфигурации \*\* Configuration Manager (DeviceComplianceOnboardingPackage.zip), который вы скачали из мастера подбора службы.</span><span class="sxs-lookup"><span data-stu-id="aad0d-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="aad0d-109">Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="aad0d-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="aad0d-110">В области навигации выберите **"Параметры** для входящего  >  **устройства".**  >  </span><span class="sxs-lookup"><span data-stu-id="aad0d-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="aad0d-111">В поле **"Метод развертывания"** выберите **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**</span><span class="sxs-lookup"><span data-stu-id="aad0d-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="aad0d-112">Выберите **пакет загрузки** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="aad0d-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="aad0d-113">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную администраторам сети, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="aad0d-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="aad0d-114">У вас должен быть файл *DeviceComplianceOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="aad0d-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="aad0d-115">Развернем пакет, следуя шагам в статье "Пакеты и [программы System Center 2012 R2 Configuration Manager".](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="aad0d-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="aad0d-116">Выберите предопределную коллекцию устройств для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="aad0d-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="aad0d-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span><span class="sxs-lookup"><span data-stu-id="aad0d-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="aad0d-118">Убедитесь, что после установки или обновления Windows пользователи завершат OOBE.</span><span class="sxs-lookup"><span data-stu-id="aad0d-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="aad0d-119">После вбора устройства можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вложено в службу.</span><span class="sxs-lookup"><span data-stu-id="aad0d-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="aad0d-120">Дополнительные сведения см. в тесте обнаружения на новом устройстве [ATP в Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="aad0d-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="aad0d-121">Обратите внимание, что можно создать правило обнаружения в приложении Configuration Manager, чтобы постоянно проверять, было ли устройство в сети.</span><span class="sxs-lookup"><span data-stu-id="aad0d-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="aad0d-122">Приложение — это объект другого типа, чем пакет и программа.</span><span class="sxs-lookup"><span data-stu-id="aad0d-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="aad0d-123">Если устройство еще не установлено (из-за ожидающих завершения OOBE или по какой-либо другой причине), Configuration Manager будет повторно фиксировать устройство, пока правило не обнаружит изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="aad0d-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="aad0d-124">Для этого можно создать проверку правила обнаружения, если значение реестра "OnboardingState" (типа REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="aad0d-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="aad0d-125">Это значение реестра находится в "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="aad0d-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="aad0d-126">Дополнительные сведения [см. в подстроке Configure Detection Methods в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="aad0d-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="aad0d-127">Настройка параметров образца коллекции</span><span class="sxs-lookup"><span data-stu-id="aad0d-127">Configure sample collection settings</span></span>

<span data-ttu-id="aad0d-128">Для каждого устройства можно установить значение конфигурации, чтобы определить, можно ли собирать образцы с устройства при отправке запроса через Центр безопасности Microsoft Defender на отправку файла для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="aad0d-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="aad0d-129">Эти параметры конфигурации обычно настраиваются с помощью Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="aad0d-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="aad0d-130">Вы можете настроить правило соответствия для элемента конфигурации в Configuration Manager, чтобы изменить пример параметра share на устройстве.</span><span class="sxs-lookup"><span data-stu-id="aad0d-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="aad0d-131">Это правило должно  быть исправлением элемента конфигурации правила соответствия, который задает значение ключа реестра на целевых устройствах, чтобы убедиться, что они жалуются.</span><span class="sxs-lookup"><span data-stu-id="aad0d-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="aad0d-132">Конфигурация заданная с помощью следующей записи реестра:</span><span class="sxs-lookup"><span data-stu-id="aad0d-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="aad0d-133">Где:</span><span class="sxs-lookup"><span data-stu-id="aad0d-133">Where:</span></span><br>
<span data-ttu-id="aad0d-134">Тип ключа — D-WORD.</span><span class="sxs-lookup"><span data-stu-id="aad0d-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="aad0d-135">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="aad0d-135">Possible values are:</span></span>
- <span data-ttu-id="aad0d-136">0 — не разрешает общий доступ к примерам с этого устройства</span><span class="sxs-lookup"><span data-stu-id="aad0d-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="aad0d-137">1 — разрешает общий доступ к файлам всех типов с этого устройства</span><span class="sxs-lookup"><span data-stu-id="aad0d-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="aad0d-138">Значение по умолчанию, если не существует ключа реестра, — 1.</span><span class="sxs-lookup"><span data-stu-id="aad0d-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="aad0d-139">Дополнительные сведения о соответствии требованиям System Center Configuration Manager см. в введении параметров соответствия [в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="aad0d-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="aad0d-140">Другие рекомендуемые параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="aad0d-140">Other recommended configuration settings</span></span>
<span data-ttu-id="aad0d-141">После включения устройств в службу важно воспользоваться преимуществами включенных возможностей защиты от угроз, включив для них следующие рекомендуемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aad0d-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="aad0d-142">Конфигурация коллекции устройств</span><span class="sxs-lookup"><span data-stu-id="aad0d-142">Device collection configuration</span></span>
<span data-ttu-id="aad0d-143">Если вы используете Endpoint Configuration Manager версии 2002 или более поздней, вы можете расширить развертывание, включив серверы или клиенты более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="aad0d-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="aad0d-144">Конфигурация защиты нового поколения</span><span class="sxs-lookup"><span data-stu-id="aad0d-144">Next generation protection configuration</span></span>

<span data-ttu-id="aad0d-145">Рекомендуется использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="aad0d-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="aad0d-146">**Сканирование**</span><span class="sxs-lookup"><span data-stu-id="aad0d-146">**Scan**</span></span>

- <span data-ttu-id="aad0d-147">Проверка съемных устройств хранения, таких как USB-накопители: да</span><span class="sxs-lookup"><span data-stu-id="aad0d-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="aad0d-148">**Защита в режиме реального времени**</span><span class="sxs-lookup"><span data-stu-id="aad0d-148">**Real-time Protection**</span></span>

- <span data-ttu-id="aad0d-149">Включить мониторинг поведения: да</span><span class="sxs-lookup"><span data-stu-id="aad0d-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="aad0d-150">Включить защиту от потенциально нежелательных приложений при загрузке и перед установкой: да</span><span class="sxs-lookup"><span data-stu-id="aad0d-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="aad0d-151">**Облачная служба защиты**</span><span class="sxs-lookup"><span data-stu-id="aad0d-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="aad0d-152">Тип членства в облачной службе защиты: расширенные членство</span><span class="sxs-lookup"><span data-stu-id="aad0d-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="aad0d-153">**Уменьшение поверхности атаки** Настройте все доступные правила для аудита.</span><span class="sxs-lookup"><span data-stu-id="aad0d-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="aad0d-154">Блокировка этих действий может прервать законные бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="aad0d-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="aad0d-155">Лучший способ — установить все для аудита, определить, какие из них безопасно включить, а затем включить эти параметры на конечных точках, которые не имеют обнаружений ложных срабатывающих результатов.</span><span class="sxs-lookup"><span data-stu-id="aad0d-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="aad0d-156">**Защита сети**</span><span class="sxs-lookup"><span data-stu-id="aad0d-156">**Network protection**</span></span>

<span data-ttu-id="aad0d-157">Перед включением защиты сети в режиме аудита или блокировки убедитесь, что установлено обновление антивластиальной платформы, которое можно получить на странице [поддержки.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="aad0d-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="aad0d-158">**Управляемый доступ к папок**</span><span class="sxs-lookup"><span data-stu-id="aad0d-158">**Controlled folder access**</span></span>

<span data-ttu-id="aad0d-159">Включить функцию в режиме аудита не менее 30 дней.</span><span class="sxs-lookup"><span data-stu-id="aad0d-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="aad0d-160">После этого просмотрите обнаружения и создайте список приложений, которые могут записывать в защищенные каталоги.</span><span class="sxs-lookup"><span data-stu-id="aad0d-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="aad0d-161">Дополнительные сведения см. в под [управлением оценки доступа к папок.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)</span><span class="sxs-lookup"><span data-stu-id="aad0d-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="aad0d-162">Отключение устройств с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aad0d-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="aad0d-163">Из соображений безопасности срок действия пакета, используемой для отключенных устройств, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="aad0d-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="aad0d-164">Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="aad0d-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="aad0d-165">При скачии пакета отключения вы будете уведомлены о дате окончания срока действия пакетов, и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="aad0d-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="aad0d-166">Политики в отношении подключения и отключения не должны развертываться одновременно на одном устройстве, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="aad0d-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="aad0d-167">Отключение устройств с помощью текущей ветви Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aad0d-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="aad0d-168">Если вы используете текущую ветвь Microsoft Endpoint Configuration Manager, см. статью "Создание файла конфигурации [отключения".](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="aad0d-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="aad0d-169">Отключение устройств с System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aad0d-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="aad0d-170">Получите пакет отключения из Центра [соответствия требованиям Майкрософт:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="aad0d-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="aad0d-171">В области навигации выберите **параметры** отключения устройства.  >    >  </span><span class="sxs-lookup"><span data-stu-id="aad0d-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="aad0d-172">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="aad0d-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="aad0d-173">В поле **"Метод развертывания"** выберите **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**</span><span class="sxs-lookup"><span data-stu-id="aad0d-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="aad0d-174">Выберите **пакет загрузки** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="aad0d-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="aad0d-175">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную администраторам сети, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="aad0d-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="aad0d-176">У вас должен быть файл *с именем DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="aad0d-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="aad0d-177">Развернем пакет, следуя шагам в статье "Пакеты и [программы System Center 2012 R2 Configuration Manager".](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="aad0d-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="aad0d-178">Выберите предопределную коллекцию устройств для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="aad0d-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aad0d-179">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него есть, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="aad0d-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="aad0d-180">Отслеживание конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="aad0d-180">Monitor device configuration</span></span>

<span data-ttu-id="aad0d-181">Если вы используете текущую ветвь Microsoft Endpoint Configuration Manager, используйте встроенную панель мониторинга ATP в Microsoft Defender в консоли Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="aad0d-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="aad0d-182">Дополнительные сведения см. в [записи "Advanced Threat Protection в Microsoft Defender - Monitor".](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="aad0d-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="aad0d-183">Если вы используете System Center 2012 R2 Configuration Manager, мониторинг состоит из двух частей:</span><span class="sxs-lookup"><span data-stu-id="aad0d-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="aad0d-184">Подтверждение правильного развертывания пакета конфигурации и его работы (или успешного запуска) на устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="aad0d-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="aad0d-185">Проверка того, что устройства соответствуют требованиям службы защиты от потери данных конечной точки Microsoft 365 (это гарантирует, что устройство сможет завершить процесс регистрации и продолжит передачу данных в службу).</span><span class="sxs-lookup"><span data-stu-id="aad0d-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="aad0d-186">Подтверждение правильного развертывания пакета конфигурации</span><span class="sxs-lookup"><span data-stu-id="aad0d-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="aad0d-187">В консоли Configuration Manager щелкните **"Мониторинг"** в нижней части области навигации.</span><span class="sxs-lookup"><span data-stu-id="aad0d-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="aad0d-188">Выберите **"Обзор",** а затем **"Развертывания".**</span><span class="sxs-lookup"><span data-stu-id="aad0d-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="aad0d-189">Выберите развертывание с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="aad0d-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="aad0d-190">Просмотрите индикаторы состояния в **статье "Статистика завершения** и **состояние содержимого".**</span><span class="sxs-lookup"><span data-stu-id="aad0d-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="aad0d-191">В случае сбойных развертывание (устройств с состоянием "Ошибка", "Требования не выполнены" или "Сбой") может потребоваться устранить неполадки. </span><span class="sxs-lookup"><span data-stu-id="aad0d-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="aad0d-192">Дополнительные сведения см. в подсети "Устранение неполадок с подмавлением [Advanced Threat Protection в Microsoft Defender".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="aad0d-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Configuration Manager с отображением успешного развертывания без ошибок](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="aad0d-194">Убедитесь, что устройства соответствуют требованиям службы защиты от потери данных Конечной точки Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aad0d-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="aad0d-195">Вы можете настроить правило соответствия для элемента конфигурации в System Center 2012 R2 Configuration Manager для отслеживания развертывания.</span><span class="sxs-lookup"><span data-stu-id="aad0d-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="aad0d-196">Эта процедура и запись реестра применимы к DLP конечной точки, а также Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="aad0d-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="aad0d-197">Это правило должно быть *элементом* конфигурации правила соответствия, который отслеживает значение ключа реестра на целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="aad0d-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="aad0d-198">Отслеживайте следующую запись реестра:</span><span class="sxs-lookup"><span data-stu-id="aad0d-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="aad0d-199">Дополнительные сведения см. [в введении параметров соответствия требованиям в System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))</span><span class="sxs-lookup"><span data-stu-id="aad0d-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aad0d-200">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="aad0d-200">Related topics</span></span>
- [<span data-ttu-id="aad0d-201">Ветвь устройств с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="aad0d-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="aad0d-202">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="aad0d-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="aad0d-203">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="aad0d-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="aad0d-204">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="aad0d-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="aad0d-205">Запуск теста обнаружения на новом устройстве ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aad0d-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="aad0d-206">Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aad0d-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
