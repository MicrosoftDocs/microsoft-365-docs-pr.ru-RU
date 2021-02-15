---
title: Подключение устройств Windows 10 с помощью локального сценария
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
description: Используйте локальный сценарий для развертывания пакета конфигурации на устройствах, чтобы они были в сети службы.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769474"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="d74cd-103">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="d74cd-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="d74cd-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d74cd-104">**Applies to:**</span></span>

- [<span data-ttu-id="d74cd-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="d74cd-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="d74cd-106">Вы также можете вручную подавить отдельные устройства для защиты от потери данных конечной точки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d74cd-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="d74cd-107">Это может потребоваться сначала при тестировании службы, прежде чем приметь все устройства в сети.</span><span class="sxs-lookup"><span data-stu-id="d74cd-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d74cd-108">Этот сценарий оптимизирован для использования на 10 устройствах.</span><span class="sxs-lookup"><span data-stu-id="d74cd-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="d74cd-109">Для масштабного развертывания используйте [другие варианты развертывания.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="d74cd-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="d74cd-110">Например, вы можете развернуть сценарий в составе более чем на 10 производственных устройствах, используя групповую [политику.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="d74cd-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="d74cd-111">Ветвь устройств</span><span class="sxs-lookup"><span data-stu-id="d74cd-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="d74cd-112">Откройте ZIP-файл пакета конфигурации GP *(DeviceComplianceOnboardingPackage.zip),* который вы скачали из мастера подбора службы.</span><span class="sxs-lookup"><span data-stu-id="d74cd-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="d74cd-113">Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d74cd-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="d74cd-114">В области навигации выберите **"Настройка**  >  **устройства" для входящего в нее устройства.**</span><span class="sxs-lookup"><span data-stu-id="d74cd-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="d74cd-115">В поле **"Метод развертывания"** выберите **локальный сценарий.**</span><span class="sxs-lookup"><span data-stu-id="d74cd-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="d74cd-116">Щелкните **"Скачать пакет"** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="d74cd-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="d74cd-117">Извлекать содержимое пакета конфигурации в расположение на устройстве, которое вы хотите в нее в комплекте (например, на настольном компьютере).</span><span class="sxs-lookup"><span data-stu-id="d74cd-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="d74cd-118">У вас должен быть файл *DeviceOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="d74cd-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="d74cd-119">Откройте командную строку с повышенными повышенными уровнями на устройстве и запустите сценарий:</span><span class="sxs-lookup"><span data-stu-id="d74cd-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="d74cd-120">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d74cd-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="d74cd-121">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="d74cd-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![Меню "Пуск" окна, указывав на запуск от администратора](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="d74cd-123">Введите расположение файла сценария.</span><span class="sxs-lookup"><span data-stu-id="d74cd-123">Type the location of the script file.</span></span> <span data-ttu-id="d74cd-124">Если файл скопирован на рабочий стол, введите: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="d74cd-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="d74cd-125">Нажмите **клавишу ВВОД** или нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="d74cd-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="d74cd-126">Сведения о том, как вручную проверить соответствие устройства требованиям и правильно сообщить данные датчиков, см. в подсети "Устранение неполадок с подсетями Advanced Threat Protection в [Microsoft Defender".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="d74cd-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="d74cd-127">Отключение устройств с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="d74cd-127">Offboard devices using a local script</span></span>
<span data-ttu-id="d74cd-128">Из соображений безопасности срок действия пакета, используемой для отключенных устройств, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="d74cd-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="d74cd-129">Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="d74cd-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="d74cd-130">При скачии пакета отключения вы будете уведомлены о дате окончания срока действия пакетов, и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="d74cd-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="d74cd-131">Политики в отношении подключения и отключения не должны развертываться одновременно на одном устройстве, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="d74cd-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="d74cd-132">Получить пакет отключения из Центра [соответствия требованиям Майкрософт](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d74cd-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="d74cd-133">В области навигации выберите **"Отключение устройства**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="d74cd-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="d74cd-134">В поле **"Метод развертывания"** выберите **локальный сценарий.**</span><span class="sxs-lookup"><span data-stu-id="d74cd-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="d74cd-135">Щелкните **"Скачать пакет"** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="d74cd-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="d74cd-136">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную устройствам.</span><span class="sxs-lookup"><span data-stu-id="d74cd-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="d74cd-137">У вас должен быть файл *с именем DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="d74cd-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="d74cd-138">Откройте командную строку с повышенными повышенными уровнями на устройстве и запустите сценарий:</span><span class="sxs-lookup"><span data-stu-id="d74cd-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="d74cd-139">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d74cd-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="d74cd-140">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="d74cd-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![Меню "Пуск" окна, указывав на запуск от администратора](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="d74cd-142">Введите расположение файла сценария.</span><span class="sxs-lookup"><span data-stu-id="d74cd-142">Type the location of the script file.</span></span> <span data-ttu-id="d74cd-143">Если файл скопирован на рабочий стол, введите: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="d74cd-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="d74cd-144">Нажмите **клавишу ВВОД** или нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="d74cd-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d74cd-145">Отключение приводит к остановке отправки устройством данных датчиков на портал.</span><span class="sxs-lookup"><span data-stu-id="d74cd-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="d74cd-146">Отслеживание конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="d74cd-146">Monitor device configuration</span></span>
<span data-ttu-id="d74cd-147">Вы можете выполнять различные действия проверки в [Устранение неполадок с подсетями](), чтобы убедиться, что сценарий успешно выполнен и агент https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) запущен.</span><span class="sxs-lookup"><span data-stu-id="d74cd-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="d74cd-148">Мониторинг также можно сделать непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="d74cd-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="d74cd-149">Мониторинг устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="d74cd-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="d74cd-150">Перейдите в [Центр соответствия требованиям Microsoft 365.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d74cd-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="d74cd-151">Выберите **"Параметры**  >  **устройств для входящего**  >  **устройства".**</span><span class="sxs-lookup"><span data-stu-id="d74cd-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="d74cd-152">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="d74cd-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d74cd-153">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d74cd-153">Related topics</span></span>
- [<span data-ttu-id="d74cd-154">Ветвь устройств с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="d74cd-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="d74cd-155">Ветвь устройств с Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d74cd-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="d74cd-156">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="d74cd-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="d74cd-157">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="d74cd-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="d74cd-158">Запуск теста обнаружения на новом устройстве ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d74cd-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="d74cd-159">Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d74cd-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
