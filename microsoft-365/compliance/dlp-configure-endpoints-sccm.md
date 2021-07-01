---
title: Подключение устройств Windows 10 с помощью Configuration Manager
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
description: Используйте Диспетчер конфигурации для развертывания пакета конфигурации на устройствах, чтобы они были размещены в службе.
ms.openlocfilehash: d2db35e50d31a0a19076965da6dcecf9cfeef826
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226901"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="66bad-103">Подключение устройств Windows 10 с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="66bad-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="66bad-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="66bad-104">**Applies to:**</span></span>

- [<span data-ttu-id="66bad-105">Microsoft 365 Предотвращение потери конечных данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="66bad-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="66bad-106">Диспетчер конфигураций System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="66bad-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="66bad-107">Бортовых устройств с System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="66bad-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="66bad-108">Откройте пакет конфигурации Configuration Manager .zip файл *(DeviceComplianceOnboardingPackage.zip), загруженный* из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="66bad-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="66bad-109">Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="66bad-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="66bad-110">В области навигации выберите **Параметры**  >  **onboarding**  >  устройства.</span><span class="sxs-lookup"><span data-stu-id="66bad-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="66bad-111">В поле **Метод развертывания** выберите Microsoft Endpoint Configuration Manager **2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="66bad-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>

4. <span data-ttu-id="66bad-112">Выберите **пакет Загрузка** и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="66bad-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="66bad-113">Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="66bad-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="66bad-114">У вас должен быть файл с именем *DeviceComplianceOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="66bad-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="66bad-115">Развертывание пакета, следуя шагам в статье [Packages and Programs System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66bad-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="66bad-116">Выберите предопределяемую коллекцию устройств для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="66bad-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="66bad-117">Microsoft 365 Предотвращение потери данных конечной точки не поддерживает вовне на этапе [Out-Of-Box Experience (OOBE).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)</span><span class="sxs-lookup"><span data-stu-id="66bad-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="66bad-118">Убедитесь, что пользователи заполняют OOBE после Windows установки или обновления.</span><span class="sxs-lookup"><span data-stu-id="66bad-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

> [!TIP]
> <span data-ttu-id="66bad-119">После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу.</span><span class="sxs-lookup"><span data-stu-id="66bad-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="66bad-120">Дополнительные сведения см. в таблице Выполнить тест обнаружения на недавно созданном [устройстве Microsoft Defender для конечных точек.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="66bad-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="66bad-121">Обратите внимание, что в приложении Configuration Manager можно создать правило обнаружения, чтобы постоянно проверять, было ли устройство на борту.</span><span class="sxs-lookup"><span data-stu-id="66bad-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="66bad-122">Приложение — это другой тип объекта, чем пакет и программа.</span><span class="sxs-lookup"><span data-stu-id="66bad-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="66bad-123">Если устройство еще не установлено (в связи с завершением OOBE или по какой-либо другой причине), диспетчер конфигурации будет повторно фиксироваться на борту устройства до тех пор, пока правило не обнаружит изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="66bad-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
>
> <span data-ttu-id="66bad-124">Это поведение может быть выполнено путем проверки правила обнаружения, если значение реестра "OnboardingState" (типа REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="66bad-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="66bad-125">Это значение реестра расположено в статье "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="66bad-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="66bad-126">Дополнительные сведения см. в [руб. В System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)</span><span class="sxs-lookup"><span data-stu-id="66bad-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="66bad-127">Настройка параметров коллекции образцов</span><span class="sxs-lookup"><span data-stu-id="66bad-127">Configure sample collection settings</span></span>

<span data-ttu-id="66bad-128">Для каждого устройства можно установить значение конфигурации, чтобы определить, можно ли собирать образцы с устройства при Центр безопасности в Microsoft Defender отправки файла для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="66bad-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="66bad-129">Эти параметры конфигурации обычно делаются с помощью Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="66bad-129">These configuration settings are typically done through Configuration Manager.</span></span>

<span data-ttu-id="66bad-130">Вы можете установить правило соответствия требованиям для элемента конфигурации в диспетчере конфигурации, чтобы изменить пример параметров обмена данными на устройстве.</span><span class="sxs-lookup"><span data-stu-id="66bad-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="66bad-131">Это правило должно быть *элементом* настройки правил соответствия требованиям, который задает значение ключа реестра на целевых устройствах, чтобы убедиться, что они являются жалобами.</span><span class="sxs-lookup"><span data-stu-id="66bad-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="66bad-132">Конфигурация заданная с помощью следующей записи ключа реестра:</span><span class="sxs-lookup"><span data-stu-id="66bad-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="66bad-133">Где:</span><span class="sxs-lookup"><span data-stu-id="66bad-133">Where:</span></span><br>
<span data-ttu-id="66bad-134">Тип ключа — это D-WORD.</span><span class="sxs-lookup"><span data-stu-id="66bad-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="66bad-135">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="66bad-135">Possible values are:</span></span>
- <span data-ttu-id="66bad-136">0 — не разрешает общий доступ к примеру с этого устройства</span><span class="sxs-lookup"><span data-stu-id="66bad-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="66bad-137">1 — позволяет обмениваться всеми типами файлов с этого устройства</span><span class="sxs-lookup"><span data-stu-id="66bad-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="66bad-138">Значение по умолчанию в случае, если ключ реестра не существует, составляет 1.</span><span class="sxs-lookup"><span data-stu-id="66bad-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="66bad-139">Дополнительные сведения о соблюдении System Center Configuration Manager см. в введении параметров соответствия требованиям [в System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66bad-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="66bad-140">Другие рекомендуемые параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="66bad-140">Other recommended configuration settings</span></span>
<span data-ttu-id="66bad-141">После включения устройств в службу важно воспользоваться включенными возможностями защиты от угроз, включив их в следующие рекомендуемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="66bad-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="66bad-142">Конфигурация коллекции устройств</span><span class="sxs-lookup"><span data-stu-id="66bad-142">Device collection configuration</span></span>
<span data-ttu-id="66bad-143">Если используется диспетчер конфигурации конечной точки версии 2002 или более поздней версии, можно расширить развертывание, включив серверы или клиенты на более позднем уровне.</span><span class="sxs-lookup"><span data-stu-id="66bad-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="66bad-144">Конфигурация защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="66bad-144">Next generation protection configuration</span></span>

<span data-ttu-id="66bad-145">Рекомендуется использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="66bad-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="66bad-146">**Сканирование**</span><span class="sxs-lookup"><span data-stu-id="66bad-146">**Scan**</span></span>

- <span data-ttu-id="66bad-147">Сканирование съемных устройств хранения, таких как USB-накопители: Да</span><span class="sxs-lookup"><span data-stu-id="66bad-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="66bad-148">**Защита в режиме реального времени**</span><span class="sxs-lookup"><span data-stu-id="66bad-148">**Real-time Protection**</span></span>

- <span data-ttu-id="66bad-149">Включить поведенческий мониторинг: Да</span><span class="sxs-lookup"><span data-stu-id="66bad-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="66bad-150">Включить защиту от потенциально нежелательных приложений при загрузке и до установки: Да</span><span class="sxs-lookup"><span data-stu-id="66bad-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="66bad-151">**Служба облачной защиты**</span><span class="sxs-lookup"><span data-stu-id="66bad-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="66bad-152">Тип членства в службе облачной защиты: расширенный членский состав</span><span class="sxs-lookup"><span data-stu-id="66bad-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="66bad-153">**Уменьшение поверхности атаки** Настройка всех доступных правил для аудита.</span><span class="sxs-lookup"><span data-stu-id="66bad-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

> [!NOTE]
> <span data-ttu-id="66bad-154">Блокировка этих действий может прервать законные бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="66bad-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="66bad-155">Оптимальный подход — настройка всех параметров аудита, определение безопасных для включения и включение параметров конечных точек, не обнаруживающих ложных срабатывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="66bad-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="66bad-156">**Защита сети**</span><span class="sxs-lookup"><span data-stu-id="66bad-156">**Network protection**</span></span>

<span data-ttu-id="66bad-157">Перед включением сетевой защиты в режиме аудита или блокировки убедитесь, что вы установили обновление платформы антивирусных программ, которое можно получить на странице [поддержки.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="66bad-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="66bad-158">**Контролируемый доступ к папкам**</span><span class="sxs-lookup"><span data-stu-id="66bad-158">**Controlled folder access**</span></span>

<span data-ttu-id="66bad-159">Включить функцию в режиме аудита не менее 30 дней.</span><span class="sxs-lookup"><span data-stu-id="66bad-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="66bad-160">После этого периода просмотрите обнаружения и создайте список приложений, которые могут записываться в защищенные каталоги.</span><span class="sxs-lookup"><span data-stu-id="66bad-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="66bad-161">Дополнительные сведения см. в [дополнительных сведениях о доступе к управляемым папкам.](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)</span><span class="sxs-lookup"><span data-stu-id="66bad-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="66bad-162">Offboard devices using Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="66bad-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="66bad-163">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="66bad-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="66bad-164">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="66bad-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="66bad-165">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="66bad-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="66bad-166">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="66bad-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="66bad-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span><span class="sxs-lookup"><span data-stu-id="66bad-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="66bad-168">Если вы используете текущую Microsoft Endpoint Configuration Manager, см. статью Создание файла конфигурации [offboarding.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)</span><span class="sxs-lookup"><span data-stu-id="66bad-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="66bad-169">Offboard devices using System Center R2 Configuration Manager 2012</span><span class="sxs-lookup"><span data-stu-id="66bad-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="66bad-170">Получите пакет offboarding из [Центра соответствия требованиям Майкрософт:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="66bad-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="66bad-171">В области навигации выберите **Параметры**  >   **устройства, включающее** >  **offboarding.**</span><span class="sxs-lookup"><span data-stu-id="66bad-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="66bad-172">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="66bad-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="66bad-173">В поле **Метод развертывания** выберите Microsoft Endpoint Configuration Manager **2012/2012 R2/1511/1602**.</span><span class="sxs-lookup"><span data-stu-id="66bad-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>

5. <span data-ttu-id="66bad-174">Выберите **пакет Загрузка** и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="66bad-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="66bad-175">Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="66bad-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="66bad-176">У вас должен быть *файл с DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="66bad-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="66bad-177">Развертывание пакета, следуя шагам в статье [Packages and Programs System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66bad-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="66bad-178">Выберите предопределяемую коллекцию устройств для развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="66bad-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66bad-179">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="66bad-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="66bad-180">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="66bad-180">Monitor device configuration</span></span>

<span data-ttu-id="66bad-181">Если вы используете текущую Microsoft Endpoint Configuration Manager, используйте встроенную панель мониторинга Microsoft Defender для конечных точек в консоли Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="66bad-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="66bad-182">Дополнительные сведения см. в [сайте Microsoft Defender Advanced Threat Protection - Monitor.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)</span><span class="sxs-lookup"><span data-stu-id="66bad-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="66bad-183">Если вы используете System Center 2012 R2 Configuration Manager, мониторинг состоит из двух частей:</span><span class="sxs-lookup"><span data-stu-id="66bad-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="66bad-184">Подтверждение правильного развертывания пакета конфигурации и успешного запуска (или успешного запуска) на устройствах в сети.</span><span class="sxs-lookup"><span data-stu-id="66bad-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="66bad-185">Проверка того, что устройства соответствуют Microsoft 365 службе предотвращения потери данных конечной точки (это гарантирует, что устройство может завершить процесс бортовой обработки и может продолжать сообщать данные в службу).</span><span class="sxs-lookup"><span data-stu-id="66bad-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="66bad-186">Подтверждение правильного развертывания пакета конфигурации</span><span class="sxs-lookup"><span data-stu-id="66bad-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="66bad-187">В консоли Configuration Manager щелкните **Мониторинг** в нижней части панели навигации.</span><span class="sxs-lookup"><span data-stu-id="66bad-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="66bad-188">Выберите **Обзор** и **развертывание.**</span><span class="sxs-lookup"><span data-stu-id="66bad-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="66bad-189">Выберите развертывание с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="66bad-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="66bad-190">Просмотрите индикаторы состояния в **статье Статистика завершения** и состояние **контента.**</span><span class="sxs-lookup"><span data-stu-id="66bad-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="66bad-191">При сбойных развертываниях (устройствах с ошибками, невыполнением требований или сбойных состояниях) может потребоваться устранение неполадок устройств.</span><span class="sxs-lookup"><span data-stu-id="66bad-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="66bad-192">Дополнительные сведения см. в выпуске [Устранение неполадок с защитой](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)от расширенных угроз Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="66bad-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Диспетчер конфигурации, показывающий успешное развертывание без ошибок](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="66bad-194">Убедитесь, что устройства соответствуют службе предотвращения Microsoft 365 конечной потери данных</span><span class="sxs-lookup"><span data-stu-id="66bad-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="66bad-195">Вы можете установить правило соответствия требованиям для элемента конфигурации System Center 2012 R2 Configuration Manager для мониторинга развертывания.</span><span class="sxs-lookup"><span data-stu-id="66bad-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="66bad-196">Эта процедура и запись реестра применяются к конечной точке DLP, а также advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="66bad-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="66bad-197">Это правило должно быть *элементом* конфигурации правил соответствия требованиям, который отслеживает значение ключа реестра на целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="66bad-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="66bad-198">Мониторинг следующей записи ключа реестра:</span><span class="sxs-lookup"><span data-stu-id="66bad-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="66bad-199">Дополнительные сведения см. в введении параметров соответствия требованиям [в System Center R2 Configuration Manager 2012.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66bad-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="66bad-200">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="66bad-200">Related topics</span></span>
- [<span data-ttu-id="66bad-201">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="66bad-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="66bad-202">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="66bad-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="66bad-203">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="66bad-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="66bad-204">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="66bad-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="66bad-205">Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="66bad-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="66bad-206">Устранение неполадок с бортовой защитой расширенных угроз Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="66bad-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)