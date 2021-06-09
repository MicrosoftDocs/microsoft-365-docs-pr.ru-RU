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
description: Чтобы развернуть пакет конфигурации на устройствах, чтобы они были на борту службы, используйте локальный скрипт.
ms.openlocfilehash: 55109d8fda52db6651d4398cd84ffd6668b4d871
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843450"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="9644f-103">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="9644f-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="9644f-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9644f-104">**Applies to:**</span></span>

- [<span data-ttu-id="9644f-105">Microsoft 365 Предотвращение потери конечных данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="9644f-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="9644f-106">Вы также можете вручную использовать отдельные устройства для Microsoft 365 предотвращения потери данных конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9644f-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="9644f-107">Это может потребоваться сначала при тестировании службы, прежде чем взять на себя обязательства по вмеяниям всех устройств в сети.</span><span class="sxs-lookup"><span data-stu-id="9644f-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9644f-108">Этот скрипт оптимизирован для использования на 10 устройствах.</span><span class="sxs-lookup"><span data-stu-id="9644f-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="9644f-109">Для развертывания в масштабе используйте [другие параметры развертывания.](dlp-configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="9644f-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="9644f-110">Например, можно развернуть сценарий onboarding на более чем 10 устройствах в производстве со сценарием, доступным на Windows 10 устройствах с помощью [групповой политики.](dlp-configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="9644f-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="9644f-111">Подключение устройств</span><span class="sxs-lookup"><span data-stu-id="9644f-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="9644f-112">Откройте пакет конфигурации GP .zip *(DeviceComplianceOnboardingPackage.zip),* который вы скачали из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="9644f-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="9644f-113">Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9644f-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="9644f-114">В области навигации выберите **Параметры**  >  **устройства.**</span><span class="sxs-lookup"><span data-stu-id="9644f-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="9644f-115">В поле **Метод развертывания** выберите **локальный скрипт**.</span><span class="sxs-lookup"><span data-stu-id="9644f-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="9644f-116">Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="9644f-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="9644f-117">Извлечение содержимого пакета конфигурации в расположение на устройстве, которое необходимо на борту (например, на рабочем столе).</span><span class="sxs-lookup"><span data-stu-id="9644f-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="9644f-118">У вас должен быть файл *с именем DeviceOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="9644f-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="9644f-119">Откройте повышенную командную строку на устройстве и запустите сценарий:</span><span class="sxs-lookup"><span data-stu-id="9644f-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="9644f-120">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9644f-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="9644f-121">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="9644f-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Меню Пуск окна, указывав на запуск в качестве администратора](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="9644f-123">Введите расположение файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="9644f-123">Type the location of the script file.</span></span> <span data-ttu-id="9644f-124">Если вы скопировали файл на рабочий стол, введите: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="9644f-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="9644f-125">Нажмите **клавишу Ввод** или нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="9644f-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="9644f-126">Сведения о том, как вручную проверить соответствие устройству и правильно сообщать данные датчика см. в статью Устранение неполадок Расширенная защита от угроз в Microsoft Defender бортовых [проблем.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="9644f-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="9644f-127">Offboard devices using a local script</span><span class="sxs-lookup"><span data-stu-id="9644f-127">Offboard devices using a local script</span></span>
<span data-ttu-id="9644f-128">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="9644f-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="9644f-129">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="9644f-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="9644f-130">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="9644f-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="9644f-131">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="9644f-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="9644f-132">Получить пакет offboarding из [Центра соответствия требованиям Майкрософт](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9644f-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="9644f-133">В области навигации выберите **Параметры**  >  **offboarding устройства.**</span><span class="sxs-lookup"><span data-stu-id="9644f-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="9644f-134">В поле **Метод развертывания** выберите **локальный скрипт**.</span><span class="sxs-lookup"><span data-stu-id="9644f-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="9644f-135">Нажмите **кнопку Загрузка** пакета и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="9644f-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="9644f-136">Извлечение содержимого файла .zip в общее расположение только для чтения, к нему можно получить доступ на устройствах.</span><span class="sxs-lookup"><span data-stu-id="9644f-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="9644f-137">У вас должен быть *файл с DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="9644f-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="9644f-138">Откройте повышенную командную строку на устройстве и запустите сценарий:</span><span class="sxs-lookup"><span data-stu-id="9644f-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="9644f-139">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9644f-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="9644f-140">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="9644f-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

    ![Меню Пуск окна, указывав на запуск в качестве администратора](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="9644f-142">Введите расположение файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="9644f-142">Type the location of the script file.</span></span> <span data-ttu-id="9644f-143">Если вы скопировали файл на рабочий стол, введите: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span><span class="sxs-lookup"><span data-stu-id="9644f-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="9644f-144">Нажмите **клавишу Ввод** или нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="9644f-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9644f-145">Отключение приводит к остановке отправки данных датчиков на портал.</span><span class="sxs-lookup"><span data-stu-id="9644f-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="9644f-146">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="9644f-146">Monitor device configuration</span></span>
<span data-ttu-id="9644f-147">Вы можете следовать различным шагам проверки в [Устранение неполадок в бортовых проблемах]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding), чтобы убедиться, что сценарий выполнен успешно и агент запущен.</span><span class="sxs-lookup"><span data-stu-id="9644f-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="9644f-148">Мониторинг также можно сделать непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="9644f-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="9644f-149">Мониторинг устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="9644f-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="9644f-150">Перейдите [Microsoft 365 центр соответствия](https://compliance.microsoft.com)требованиям.</span><span class="sxs-lookup"><span data-stu-id="9644f-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="9644f-151">Выберите **Параметры**  >  **устройства.**  >  </span><span class="sxs-lookup"><span data-stu-id="9644f-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="9644f-152">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="9644f-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9644f-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9644f-153">Related topics</span></span>
- [<span data-ttu-id="9644f-154">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="9644f-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="9644f-155">На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9644f-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="9644f-156">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="9644f-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="9644f-157">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="9644f-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="9644f-158">Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="9644f-158">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="9644f-159">Устранение неполадок Расширенная защита от угроз в Microsoft Defender бортовых проблем</span><span class="sxs-lookup"><span data-stu-id="9644f-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)