---
title: Встроенные устройства с Windows 10 с помощью локального сценария
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
description: Используйте локальный скрипт для развертывания пакета конфигурации на устройствах, чтобы они были подключены к службе.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769474"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="ac58b-103">Встроенные устройства с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="ac58b-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="ac58b-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ac58b-104">**Applies to:**</span></span>

- [<span data-ttu-id="ac58b-105">Защита от потери данных (DLP) Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac58b-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="ac58b-106">Вы также можете вручную подключить отдельные устройства к предотвращению потери данных в конечной точке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac58b-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="ac58b-107">Это может потребоваться в первую очередь при тестировании службы перед выполнением входящей миграции всех устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="ac58b-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac58b-108">Этот сценарий оптимизирован для использования на 10 устройствах.</span><span class="sxs-lookup"><span data-stu-id="ac58b-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="ac58b-109">Чтобы развернуть масштаб на уровне, используйте [другие варианты развертывания](dlp-configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="ac58b-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="ac58b-110">Например, вы можете развернуть сценарий входящей миграции на более чем 10 устройствах в рабочей среде, используя скрипт, доступный на встроенных [устройствах Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md).</span><span class="sxs-lookup"><span data-stu-id="ac58b-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="ac58b-111">Встроенные устройства</span><span class="sxs-lookup"><span data-stu-id="ac58b-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="ac58b-112">Откройте ZIP-файл пакета конфигурации GP ( *DeviceComplianceOnboardingPackage.zip* ), скачанный с помощью мастера входящей миграции служб.</span><span class="sxs-lookup"><span data-stu-id="ac58b-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ac58b-113">Вы также можете получить пакет из [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ac58b-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="ac58b-114">В области навигации выберите приподключение **Settings**  >  **устройства** параметров.</span><span class="sxs-lookup"><span data-stu-id="ac58b-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="ac58b-115">В поле **метод развертывания** выберите **локальный скрипт** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="ac58b-116">Нажмите кнопку **загрузить пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="ac58b-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="ac58b-117">Извлеките содержимое пакета конфигурации в расположение на устройстве, которое вы хотите подключить (например, на рабочем столе).</span><span class="sxs-lookup"><span data-stu-id="ac58b-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="ac58b-118">У вас должен быть файл с именем *девицеонбоардингскрипт. cmd* .</span><span class="sxs-lookup"><span data-stu-id="ac58b-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="ac58b-119">Откройте командную строку с повышенными привилегиями на устройстве и выполните сценарий:</span><span class="sxs-lookup"><span data-stu-id="ac58b-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="ac58b-120">В меню **Пуск** выберите **команду cmd** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="ac58b-121">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите пункт **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Меню "Пуск" в окне "Запуск от имени администратора"](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="ac58b-123">Введите путь к файлу скрипта.</span><span class="sxs-lookup"><span data-stu-id="ac58b-123">Type the location of the script file.</span></span> <span data-ttu-id="ac58b-124">Если вы скопировали файл на Рабочий стол, введите: *%усерпрофиле%\десктоп\виндовсдефендератпонбоардингскрипт.КМД*</span><span class="sxs-lookup"><span data-stu-id="ac58b-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="ac58b-125">Нажмите клавишу **Ввод** или кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="ac58b-126">Сведения о том, как вручную проверить соответствие устройства требованиям и правильно сообщать данные датчиков, можно в [статье Устранение неполадок, связанных с защитой Advanced Threat Protection в защитнике Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="ac58b-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="ac58b-127">Устройства переносе с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="ac58b-127">Offboard devices using a local script</span></span>
<span data-ttu-id="ac58b-128">Из соображений безопасности для пакета, используемого для переносе устройств, срок действия истекает через 30 дней после загрузки даты.</span><span class="sxs-lookup"><span data-stu-id="ac58b-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="ac58b-129">Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="ac58b-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="ac58b-130">При загрузке пакета отключения вы получите уведомление об истечении срока действия пакетов, и оно также будет включено в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="ac58b-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="ac58b-131">Входящая и исходящая политики не должны разворачиваться на одном устройстве одновременно, в противном случае это приведет к непредсказуемым конфликтам.</span><span class="sxs-lookup"><span data-stu-id="ac58b-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="ac58b-132">Получение пакета отключения от [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ac58b-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="ac58b-133">В области навигации выберите параметры отключение **Settings**  >  **устройства** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="ac58b-134">В поле **метод развертывания** выберите **локальный скрипт** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="ac58b-135">Нажмите кнопку **загрузить пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="ac58b-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="ac58b-136">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную для устройств.</span><span class="sxs-lookup"><span data-stu-id="ac58b-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="ac58b-137">У вас должен быть файл с именем *DeviceComplianceOffboardingScript_valid_until_YYYY-мм-дд. cmd* .</span><span class="sxs-lookup"><span data-stu-id="ac58b-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="ac58b-138">Откройте командную строку с повышенными привилегиями на устройстве и выполните сценарий:</span><span class="sxs-lookup"><span data-stu-id="ac58b-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="ac58b-139">В меню **Пуск** выберите **команду cmd** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="ac58b-140">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите пункт **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Меню "Пуск" в окне "Запуск от имени администратора"](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="ac58b-142">Введите путь к файлу скрипта.</span><span class="sxs-lookup"><span data-stu-id="ac58b-142">Type the location of the script file.</span></span> <span data-ttu-id="ac58b-143">Если вы скопировали файл на Рабочий стол, введите: *%усерпрофиле%\десктоп\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-мм-дд. cmd*</span><span class="sxs-lookup"><span data-stu-id="ac58b-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="ac58b-144">Нажмите клавишу **Ввод** или кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac58b-145">Отключение приводит к тому, что устройство не отправляет данные датчиков на портал.</span><span class="sxs-lookup"><span data-stu-id="ac58b-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="ac58b-146">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="ac58b-146">Monitor device configuration</span></span>
<span data-ttu-id="ac58b-147">Вы можете выполнить действия, описанные в разделе [Устранение неполадок при подключении] (( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) чтобы убедиться, что сценарий успешно выполнен и агент запущен.</span><span class="sxs-lookup"><span data-stu-id="ac58b-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="ac58b-148">Мониторинг можно также выполнить непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="ac58b-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="ac58b-149">Отслеживание устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="ac58b-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="ac58b-150">Перейдите в [центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ac58b-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="ac58b-151">Выберите **Settings**  >  **Devices to Board** Devices (параметры)  >  **Devices** .</span><span class="sxs-lookup"><span data-stu-id="ac58b-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="ac58b-152">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="ac58b-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ac58b-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ac58b-153">Related topics</span></span>
- [<span data-ttu-id="ac58b-154">Встроенные устройства с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="ac58b-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="ac58b-155">Встроенные устройства с Windows 10 с помощью диспетчера конфигураций конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ac58b-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="ac58b-156">Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="ac58b-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="ac58b-157">Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="ac58b-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="ac58b-158">Запуск проверки обнаружения на неподключенном устройстве "защитник Майкрософт" в автономном выплате</span><span class="sxs-lookup"><span data-stu-id="ac58b-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="ac58b-159">Устранение неполадок, связанных с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ac58b-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
