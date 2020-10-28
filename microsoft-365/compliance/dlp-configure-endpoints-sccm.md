---
title: Встроенные устройства с Windows 10 с помощью диспетчера конфигураций
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
description: С помощью Configuration Manager разверните пакет конфигурации на устройствах, чтобы они были подключены к службе.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769475"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="7cfc9-103">Встроенные устройства с Windows 10 с помощью диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="7cfc9-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="7cfc9-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7cfc9-104">**Applies to:**</span></span>

- [<span data-ttu-id="7cfc9-105">Защита от потери данных (DLP) Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="7cfc9-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="7cfc9-106">Диспетчер конфигураций System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7cfc9-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="7cfc9-107">Встроенные устройства с помощью System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7cfc9-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="7cfc9-108">Откройте ZIP-файл пакета конфигурации Configuration Manager ( *DeviceComplianceOnboardingPackage.zip* ), скачанный с помощью мастера входящей миграции служб.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="7cfc9-109">Вы также можете получить пакет из [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7cfc9-110">В области навигации выберите **Параметры** входящей миграции  >  **устройств**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="7cfc9-111">В поле **метод развертывания** выберите **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="7cfc9-112">Выберите пункт **скачать пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="7cfc9-113">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения и доступную для администраторов сети, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="7cfc9-114">У вас должен быть файл с именем *девицекомплианцеонбоардингскрипт. cmd* .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="7cfc9-115">Разверните пакет, выполнив действия, описанные в статье [packages and Programs In System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="7cfc9-116">Выберите предварительно определенную коллекцию устройств, в которую будет развернут пакет.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="7cfc9-117">Защита от потери данных в конечных точках Microsoft 365 не поддерживает входящую миграцию во время этапа [приветствия (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="7cfc9-118">Убедитесь, что пользователи завершают OOBE после установки или обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="7cfc9-119">После подключения устройства можно выбрать выполнение проверки обнаружения, чтобы убедиться, что устройство правильно подключено к службе.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="7cfc9-120">Дополнительные сведения см. в [статье выполнение проверки обнаружения для нового устройства ATP "защитник Майкрософт"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="7cfc9-121">Обратите внимание на то, что можно создать правило обнаружения для приложения Configuration Manager, чтобы постоянно проверять, было ли устройство подключено к подсистеме.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="7cfc9-122">Приложение — это тип объекта, отличный от того, который является пакетом и программой.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="7cfc9-123">Если устройство еще не подключено (из-за ожидания завершения OOBE или по какой-либо иной причине), диспетчер конфигурации попытается выполнить подключение устройства до тех пор, пока правило не обнаружит изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="7cfc9-124">Это можно сделать, создав проверку правила обнаружения, если значение реестра "Онбоардингстате" (типа REG_DWORD) = 1.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="7cfc9-125">Это значение реестра находится в разделе "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Протектион\статус".</span><span class="sxs-lookup"><span data-stu-id="7cfc9-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="7cfc9-126">Дополнительные сведения см. [в разделе configure Detection Methods In System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="7cfc9-127">Настройка параметров коллекции образцов</span><span class="sxs-lookup"><span data-stu-id="7cfc9-127">Configure sample collection settings</span></span>

<span data-ttu-id="7cfc9-128">Для каждого устройства можно задать значение конфигурации, чтобы определить, можно ли собирать данные с устройства при выполнении запроса с помощью центра безопасности защитника Майкрософт, чтобы отправить файл для детального анализа.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="7cfc9-129">Эти параметры конфигурации обычно выполняются с помощью Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="7cfc9-130">Вы можете задать правило соответствия для элемента конфигурации в диспетчере конфигураций, чтобы изменить параметр общего доступа к общему ресурсу на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="7cfc9-131">Это правило должно быть элементом конфигурации правила соответствия *Устранение* , который задает значение раздела реестра на целевых устройствах, чтобы убедиться, что они являются жалобой.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="7cfc9-132">Конфигурация задается с помощью следующей записи раздела реестра:</span><span class="sxs-lookup"><span data-stu-id="7cfc9-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="7cfc9-133">Где:</span><span class="sxs-lookup"><span data-stu-id="7cfc9-133">Where:</span></span><br>
<span data-ttu-id="7cfc9-134">Тип ключа это D-слово.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="7cfc9-135">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="7cfc9-135">Possible values are:</span></span>
- <span data-ttu-id="7cfc9-136">0 — не разрешает общий доступ к образцу с этого устройства</span><span class="sxs-lookup"><span data-stu-id="7cfc9-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="7cfc9-137">1 — разрешает общий доступ к типам файлов с этого устройства.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="7cfc9-138">Значение по умолчанию, если раздел реестра не существует — 1.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="7cfc9-139">Для получения дополнительных сведений о соответствии требованиям System Center Configuration Manager, ознакомьтесь со статьей [Введение в параметры соответствия требованиям в System center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="7cfc9-140">Другие Рекомендуемые параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="7cfc9-140">Other recommended configuration settings</span></span>
<span data-ttu-id="7cfc9-141">После подключения устройств к службе необходимо воспользоваться преимуществами включенных функций защиты от угроз, добавив их в следующие рекомендуемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="7cfc9-142">Конфигурация коллекции устройств</span><span class="sxs-lookup"><span data-stu-id="7cfc9-142">Device collection configuration</span></span>
<span data-ttu-id="7cfc9-143">Если вы используете Диспетчер конфигураций конечной точки версии 2002 или более поздней, вы можете расширить развертывание, включив в него серверы или клиенты более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="7cfc9-144">Конфигурация защиты следующего поколения</span><span class="sxs-lookup"><span data-stu-id="7cfc9-144">Next generation protection configuration</span></span>

<span data-ttu-id="7cfc9-145">Рекомендуется использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="7cfc9-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="7cfc9-146">**Сканирование**</span><span class="sxs-lookup"><span data-stu-id="7cfc9-146">**Scan**</span></span>

- <span data-ttu-id="7cfc9-147">Проверка съемных устройств хранения данных, таких как USB-накопители: Да</span><span class="sxs-lookup"><span data-stu-id="7cfc9-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="7cfc9-148">**Защита в режиме реального времени**</span><span class="sxs-lookup"><span data-stu-id="7cfc9-148">**Real-time Protection**</span></span>

- <span data-ttu-id="7cfc9-149">Включить мониторинг поведения: Да</span><span class="sxs-lookup"><span data-stu-id="7cfc9-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="7cfc9-150">Включение защиты от потенциально нежелательных приложений при скачивании и до установки: Да</span><span class="sxs-lookup"><span data-stu-id="7cfc9-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="7cfc9-151">**Служба облачной защиты**</span><span class="sxs-lookup"><span data-stu-id="7cfc9-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="7cfc9-152">Тип участия в службе облачной защиты: расширенное членство</span><span class="sxs-lookup"><span data-stu-id="7cfc9-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="7cfc9-153">**Сокращение** уязвимой зоны Настройте все доступные правила для аудита.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="7cfc9-154">Блокировка этих действий может привести к прерыванию легальных бизнес-процессов.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="7cfc9-155">Лучший подход — установить все функции аудита, определить, какие из них безопасны, а затем включить эти параметры в конечных точках, не имеющих ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="7cfc9-156">**Защита сети**</span><span class="sxs-lookup"><span data-stu-id="7cfc9-156">**Network protection**</span></span>

<span data-ttu-id="7cfc9-157">Прежде чем включить защиту сети в режиме аудита или блокировки, убедитесь, что вы установили обновление платформы для защиты от вредоносных программ, которое можно получить на [странице поддержки](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="7cfc9-158">**Контролируемый доступ к папкам**</span><span class="sxs-lookup"><span data-stu-id="7cfc9-158">**Controlled folder access**</span></span>

<span data-ttu-id="7cfc9-159">Включение функции в режиме аудита не менее 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="7cfc9-160">По истечении этого периода просмотрите определения и создайте список приложений, которым разрешено выполнять запись в защищенные каталоги.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="7cfc9-161">Более подробную информацию можно узнать в статье [Оценка контролируемого доступа к папкам](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="7cfc9-162">Устройства переносе с помощью диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="7cfc9-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="7cfc9-163">Из соображений безопасности для пакета, используемого для переносе устройств, срок действия истекает через 30 дней после загрузки даты.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="7cfc9-164">Недействительные пакеты отключения, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="7cfc9-165">При загрузке пакета отключения вы получите уведомление об истечении срока действия пакетов, и оно также будет включено в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="7cfc9-166">Входящая и исходящая политики не должны разворачиваться на одном устройстве одновременно, в противном случае это приведет к непредсказуемым конфликтам.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="7cfc9-167">Устройства переносе, использующие текущую ветвь Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7cfc9-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="7cfc9-168">Если вы используете текущую ветвь Microsoft Endpoint Configuration Manager, ознакомьтесь [со статьей Создание файла конфигурации](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)отключения.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="7cfc9-169">Устройства переносе с использованием System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7cfc9-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="7cfc9-170">Получение пакета отключения от [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="7cfc9-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="7cfc9-171">В области навигации выберите **Параметры** отключение подключения  >   **устройства** >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="7cfc9-172">Выберите Windows 10 в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="7cfc9-173">В поле **метод развертывания** выберите **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="7cfc9-174">Выберите пункт **скачать пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="7cfc9-175">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения и доступную для администраторов сети, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="7cfc9-176">У вас должен быть файл с именем *DeviceComplianceOffboardingScript_valid_until_YYYY-мм-дд. cmd* .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="7cfc9-177">Разверните пакет, выполнив действия, описанные в статье [packages and Programs In System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="7cfc9-178">Выберите предварительно определенную коллекцию устройств, в которую будет развернут пакет.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cfc9-179">Отключение останавливает отправку данных датчиков на портал, но данные с устройства, в том числе ссылки на все оповещения, которые она будет хранить, в течение 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="7cfc9-180">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="7cfc9-180">Monitor device configuration</span></span>

<span data-ttu-id="7cfc9-181">Если вы используете текущую ветвь Microsoft Endpoint Configuration Manager, используйте встроенную панель мониторинга защитника Microsoft Defender в консоли Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="7cfc9-182">Дополнительные сведения см. в разделе [Advanced Threat Protection в защитнике Майкрософт — мониторинг](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="7cfc9-183">Если вы используете System Center 2012 R2 Configuration Manager, отслеживание состоит из двух частей:</span><span class="sxs-lookup"><span data-stu-id="7cfc9-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="7cfc9-184">Подтверждение того, что пакет конфигурации был правильно развернут и запущен (или успешно запущен) на устройствах в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="7cfc9-185">Проверка того, что устройства соответствуют службе защиты от потери данных в Microsoft 365 (это гарантирует, что устройство может завершить процесс входящей миграции и может продолжать отчитываться от данных для службы).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="7cfc9-186">Подтвердите, что пакет конфигурации был правильно развернут</span><span class="sxs-lookup"><span data-stu-id="7cfc9-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="7cfc9-187">В консоли диспетчера конфигураций щелкните **мониторинг** в нижней части области навигации.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="7cfc9-188">Выберите **Обзор** , а затем **развертывания** .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="7cfc9-189">Выберите развертывание с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="7cfc9-190">Просмотрите индикаторы состояния в разделе **Статистика о завершении** и **состояние контента** .</span><span class="sxs-lookup"><span data-stu-id="7cfc9-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="7cfc9-191">Если при развертывании произошел сбой (устройства с **ошибками** , **требования не выполнены** или **состояния** с ошибками), может потребоваться устранение неполадок устройств.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="7cfc9-192">Дополнительные сведения см. в [статье Устранение неполадок, связанных с Advanced Threat Protection в защитнике Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Диспетчер конфигураций, демонстрирующий успешное развертывание без ошибок](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="7cfc9-194">Убедитесь, что устройства соответствуют службе защиты от потери данных в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cfc9-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="7cfc9-195">Для отслеживания развертывания можно задать правило соответствия для элемента конфигурации в System Center 2012 R2 Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="7cfc9-196">Эта процедура и запись реестра применяются к точке защиты от потери данных и Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="7cfc9-197">Это правило должно быть элементом конфигурации правила соответствия, не относящимся к *Устранение* , который отслеживает значение раздела реестра на целевых устройствах.</span><span class="sxs-lookup"><span data-stu-id="7cfc9-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="7cfc9-198">Отслеживайте следующую запись раздела реестра:</span><span class="sxs-lookup"><span data-stu-id="7cfc9-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="7cfc9-199">Дополнительные сведения см. [в разделе Введение в параметры соответствия требованиям в System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="7cfc9-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7cfc9-200">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7cfc9-200">Related topics</span></span>
- [<span data-ttu-id="7cfc9-201">Встроенные устройства с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="7cfc9-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="7cfc9-202">Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="7cfc9-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="7cfc9-203">Встроенные устройства с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="7cfc9-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="7cfc9-204">Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="7cfc9-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="7cfc9-205">Запуск проверки обнаружения на неподключенном устройстве "защитник Майкрософт" в автономном выплате</span><span class="sxs-lookup"><span data-stu-id="7cfc9-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="7cfc9-206">Устранение неполадок, связанных с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7cfc9-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
