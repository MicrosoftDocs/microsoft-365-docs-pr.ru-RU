---
title: Подключение устройств Windows 10 с помощью групповой политики
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Используйте групповую политику для развертывания пакета конфигурации на устройствах с Windows 10, чтобы они были в составе службы.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769449"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="84ebd-103">Ветвь устройств с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="84ebd-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="84ebd-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="84ebd-104">**Applies to:**</span></span>

- [<span data-ttu-id="84ebd-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="84ebd-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="84ebd-106">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="84ebd-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="84ebd-107">Чтобы использовать обновления групповой политики для развертывания пакета, необходимо быть на Windows Server 2008 R2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="84ebd-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="84ebd-108">В Windows Server 2019 может потребоваться заменить NT AUTHORITY\Well-Known-System-Account на NT AUTHORITY\SYSTEM XML-файла, который создается предпочтениями групповой политики.</span><span class="sxs-lookup"><span data-stu-id="84ebd-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="84ebd-109">Ветвь устройств с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="84ebd-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="84ebd-110">Откройте ZIP-файл пакета конфигурации GP *(DeviceComplianceOnboardingPackage.zip),* который вы скачали из мастера подбора службы.</span><span class="sxs-lookup"><span data-stu-id="84ebd-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="84ebd-111">Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="84ebd-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="84ebd-112">В области навигации выберите **"Настройка входящего**  >  **устройства".**</span><span class="sxs-lookup"><span data-stu-id="84ebd-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="84ebd-113">В поле **"Метод развертывания"** выберите **групповую политику.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="84ebd-114">Щелкните **"Скачать пакет"** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="84ebd-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="84ebd-115">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную устройству.</span><span class="sxs-lookup"><span data-stu-id="84ebd-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="84ebd-116">У вас должна быть папка *OptionalParamsPolicy* и файл *DeviceComplianceLocalOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="84ebd-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="84ebd-117">Откройте консоль [управления групповыми](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) политиками (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который нужно настроить, и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="84ebd-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="84ebd-118">В **редакторе управления групповыми политиками** перейдите **к** параметрам конфигурации **компьютера,** а затем к настройкам панели **управления.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="84ebd-119">Щелкните правой кнопкой мыши **запланированные задачи,** найдите пункт **"Новый"** и выберите пункт "Немедленная задача " (по крайней **мере, Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="84ebd-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="84ebd-120">В **открываемом** окне "Задача" перейдите на **вкладку "Общие".** В **области "Параметры безопасности"** щелкните **"Изменить пользователя или группу"** и введите "СИСТЕМА", а затем нажмите кнопку **"Проверить имена"** и "ОК". </span><span class="sxs-lookup"><span data-stu-id="84ebd-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="84ebd-121">NT AUTHORITY\SYSTEM отображается как учетная запись пользователя, в качестве которую будет запускаться задача.</span><span class="sxs-lookup"><span data-stu-id="84ebd-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="84ebd-122">Выберите **"Выполнить" независимо** от того, вошел ли пользователь в систему, и поимите его в поле "Выполнить с наивысшими **привилегиями".**</span><span class="sxs-lookup"><span data-stu-id="84ebd-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="84ebd-123">Перейдите на **вкладку "Действия"** и нажмите кнопку **"Новый"...** **Убедитесь, что в поле действия** выбран запуск программы. </span><span class="sxs-lookup"><span data-stu-id="84ebd-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="84ebd-124">Введите имя и расположение общего файла *WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="84ebd-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="84ebd-125">Нажмите **кнопку** "ОК" и закроем все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="84ebd-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="84ebd-126">Отключение устройств с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="84ebd-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="84ebd-127">Из соображений безопасности срок действия пакета, используемой для отключенных устройств, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="84ebd-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="84ebd-128">Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="84ebd-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="84ebd-129">При скачии пакета отключения вы будете уведомлены о дате окончания срока действия пакетов, и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="84ebd-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="84ebd-130">Политики в отношении подключения и отключения не должны развертываться одновременно на одном устройстве, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="84ebd-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="84ebd-131">Получите пакет отключения из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="84ebd-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="84ebd-132">В области навигации выберите **параметры**  >  **//Отключение входящего**  >  **устройства.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="84ebd-133">В поле **"Метод развертывания"** выберите **групповую политику.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="84ebd-134">Щелкните **"Скачать пакет"** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="84ebd-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="84ebd-135">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную устройству.</span><span class="sxs-lookup"><span data-stu-id="84ebd-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="84ebd-136">У вас должен быть файл *с именем DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="84ebd-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="84ebd-137">Откройте консоль [управления групповыми](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) политиками (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который нужно настроить, и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="84ebd-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="84ebd-138">В **редакторе управления групповыми политиками** перейдите к конфигурации **компьютера,** затем "Параметры" **и** **"Параметры панели управления".**</span><span class="sxs-lookup"><span data-stu-id="84ebd-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="84ebd-139">Щелкните правой кнопкой мыши **запланированные задачи,** найдите пункт **"Новый"** и выберите **"Немедленная задача".**</span><span class="sxs-lookup"><span data-stu-id="84ebd-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="84ebd-140">В **открываемом** окне "Задача" перейдите на **вкладку "Общие".** Выберите локализованную учетную запись пользователя SYSTEM (BUILTIN\SYSTEM) в **параметрах безопасности.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="84ebd-141">Выберите **"Выполнить" независимо** от того, вошел пользователь в систему или нет, и проверьте его с помощью контрольного окна "Выполнить с наивысшими привилегиями". </span><span class="sxs-lookup"><span data-stu-id="84ebd-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="84ebd-142">Перейдите на **вкладку "Действия"** и нажмите **кнопку "Новый"...** **Убедитесь, что в поле действия** выбран запуск программы. </span><span class="sxs-lookup"><span data-stu-id="84ebd-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="84ebd-143">Введите имя и расположение общего *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="84ebd-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="84ebd-144">Нажмите **кнопку** "ОК" и закроем все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="84ebd-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84ebd-145">Отключение приводит к остановке отправки устройством данных датчиков на портал, но с устройства.</span><span class="sxs-lookup"><span data-stu-id="84ebd-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="84ebd-146">Отслеживание конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="84ebd-146">Monitor device configuration</span></span>
<span data-ttu-id="84ebd-147">С помощью групповой политики нет возможности отслеживать развертывание политик на устройствах.</span><span class="sxs-lookup"><span data-stu-id="84ebd-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="84ebd-148">Мониторинг можно сделать непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="84ebd-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="84ebd-149">Мониторинг устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="84ebd-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="84ebd-150">Перейдите в [Центр соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="84ebd-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="84ebd-151">Щелкните **список устройств.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="84ebd-152">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="84ebd-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="84ebd-153">Отображение устройств в списке устройств может занять несколько **дней.**</span><span class="sxs-lookup"><span data-stu-id="84ebd-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="84ebd-154">Это включает время, необходимое для распространения политик на устройство, время, необходимое для входа пользователя в систему, и время, необходимое конечной точке для начала отчетности.</span><span class="sxs-lookup"><span data-stu-id="84ebd-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="84ebd-155">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="84ebd-155">Related topics</span></span>
- [<span data-ttu-id="84ebd-156">Ветвь устройств с Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="84ebd-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="84ebd-157">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="84ebd-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="84ebd-158">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="84ebd-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="84ebd-159">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="84ebd-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="84ebd-160">Запуск теста обнаружения на новых устройствах ATP в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="84ebd-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="84ebd-161">Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="84ebd-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
