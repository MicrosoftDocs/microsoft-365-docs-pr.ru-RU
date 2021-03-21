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
description: Используйте групповую политику для развертывания пакета конфигурации на устройствах с Windows 10, чтобы они были размещены в службе.
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918025"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="0e547-103">На борту устройств Windows 10 с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="0e547-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="0e547-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0e547-104">**Applies to:**</span></span>

- [<span data-ttu-id="0e547-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0e547-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="0e547-106">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="0e547-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="0e547-107">Чтобы использовать обновления групповой политики (GP) для развертывания пакета, необходимо быть на Windows Server 2008 R2 или позже.</span><span class="sxs-lookup"><span data-stu-id="0e547-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="0e547-108">Для Windows Server 2019 может потребоваться заменить NT AUTHORITY\Well-Known-System-Account на NT AUTHORITY\SYSTEM XML-файла, который создается в предпочтениях групповой политики.</span><span class="sxs-lookup"><span data-stu-id="0e547-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="0e547-109">На борту устройств с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="0e547-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="0e547-110">Откройте пакет конфигурации GP .zip file *(DeviceComplianceOnboardingPackage.zip), загруженный* из мастера бортового обслуживания.</span><span class="sxs-lookup"><span data-stu-id="0e547-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="0e547-111">Вы также можете получить пакет из [Центра соответствия требованиям Майкрософт](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="0e547-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="0e547-112">В области навигации выберите **параметры**  >  **onboarding устройства**.</span><span class="sxs-lookup"><span data-stu-id="0e547-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="0e547-113">В поле **Метод развертывания** выберите **групповую политику.**</span><span class="sxs-lookup"><span data-stu-id="0e547-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="0e547-114">Нажмите **кнопку Скачать пакет** и сохранить файл .zip.</span><span class="sxs-lookup"><span data-stu-id="0e547-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="0e547-115">Извлечение содержимого файла .zip в общее, только для чтения расположение, которое можно получить на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0e547-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="0e547-116">У вас должна быть папка *OptionalParamsPolicy* и файл *DeviceComplianceLocalOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="0e547-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="0e547-117">Откройте консоль [управления групповой](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) политикой (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0e547-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="0e547-118">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера,** затем **параметры**"Предпочтения", а затем **параметры панели управления.**</span><span class="sxs-lookup"><span data-stu-id="0e547-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="0e547-119">Щелкните правой кнопкой мыши **Запланированные задачи,** указать **на Новое,** а затем нажмите кнопку Немедленная задача **(по крайней мере Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="0e547-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="0e547-120">В **открываемом** окне Задача перейдите на **вкладку General.** В **параметрах Безопасности** нажмите **кнопку Изменить пользователя или группу** и введите SYSTEM, а затем нажмите **кнопку Check Names** then **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e547-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="0e547-121">NT AUTHORITY\SYSTEM отображается в качестве учетной записи пользователя, как будет работать задача.</span><span class="sxs-lookup"><span data-stu-id="0e547-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="0e547-122">Выберите **Выполнить, вошел** ли пользователь или нет, и проверьте поле Выполнить с **самыми** высокими привилегиями.</span><span class="sxs-lookup"><span data-stu-id="0e547-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="0e547-123">Перейдите на **вкладку Действия** и нажмите **кнопку New...** **Убедитесь, что программа Start** выбрана в поле **Действия.**</span><span class="sxs-lookup"><span data-stu-id="0e547-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="0e547-124">Введите имя файла и расположение общего *файла WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="0e547-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="0e547-125">Нажмите **кнопку ОК** и закрой все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="0e547-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="0e547-126">Offboard devices using Group Policy</span><span class="sxs-lookup"><span data-stu-id="0e547-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="0e547-127">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="0e547-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="0e547-128">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="0e547-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="0e547-129">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="0e547-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="0e547-130">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="0e547-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="0e547-131">Получите пакет offboarding из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="0e547-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="0e547-132">В области навигации выберите **Параметры**  >  **//Устройство, включающее**  >  **offboarding.**</span><span class="sxs-lookup"><span data-stu-id="0e547-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="0e547-133">В поле **Метод развертывания** выберите **групповую политику.**</span><span class="sxs-lookup"><span data-stu-id="0e547-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="0e547-134">Нажмите **кнопку Скачать пакет** и сохранить файл .zip.</span><span class="sxs-lookup"><span data-stu-id="0e547-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="0e547-135">Извлечение содержимого файла .zip в общее, только для чтения расположение, которое можно получить на устройстве.</span><span class="sxs-lookup"><span data-stu-id="0e547-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="0e547-136">У вас должен быть *файл с DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="0e547-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="0e547-137">Откройте консоль [управления групповой](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) политикой (GPMC), щелкните правой кнопкой мыши объект групповой политики (GPO), который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0e547-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="0e547-138">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера,** затем **параметры**"Предпочтения", а затем **параметры панели управления.**</span><span class="sxs-lookup"><span data-stu-id="0e547-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="0e547-139">Щелкните правой кнопкой мыши **Запланированные задачи,** указать **на Новое,** а затем нажмите **кнопку Немедленное задание**.</span><span class="sxs-lookup"><span data-stu-id="0e547-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="0e547-140">В **открываемом** окне Задача перейдите на **вкладку General.** Выберите учетную запись локального пользователя SYSTEM (BUILTIN\SYSTEM) в **параметрах Безопасности.**</span><span class="sxs-lookup"><span data-stu-id="0e547-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="0e547-141">Выберите **Выполнить, вошел** ли пользователь в систему или нет, и проверьте поле **Выполнить** с самыми высокими привилегиями.</span><span class="sxs-lookup"><span data-stu-id="0e547-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="0e547-142">Перейдите на **вкладку Действия** и нажмите **кнопку New...**. **Убедитесь, что программа Start** выбрана в поле **Действия.**</span><span class="sxs-lookup"><span data-stu-id="0e547-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="0e547-143">Введите имя файла и расположение *общего DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="0e547-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="0e547-144">Нажмите **кнопку ОК** и закрой все открытые окна GPMC.</span><span class="sxs-lookup"><span data-stu-id="0e547-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e547-145">Offboarding заставляет устройство перестать отправлять данные датчиков на портал, но данные с устройства.</span><span class="sxs-lookup"><span data-stu-id="0e547-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="0e547-146">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="0e547-146">Monitor device configuration</span></span>
<span data-ttu-id="0e547-147">В групповой политике нет возможности отслеживать развертывание политик на устройствах.</span><span class="sxs-lookup"><span data-stu-id="0e547-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="0e547-148">Мониторинг можно сделать непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="0e547-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="0e547-149">Мониторинг устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="0e547-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="0e547-150">Перейдите в Центр соответствия требованиям [Майкрософт.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="0e547-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="0e547-151">Щелкните **список Устройств.**</span><span class="sxs-lookup"><span data-stu-id="0e547-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="0e547-152">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="0e547-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="0e547-153">Для начала показа устройств в списке Устройств может занять несколько **дней.**</span><span class="sxs-lookup"><span data-stu-id="0e547-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="0e547-154">Это включает время, необходимое для распространения политик на устройство, время, необходимое для входа пользователя, и время, необходимое для начала отчетов конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="0e547-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0e547-155">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="0e547-155">Related topics</span></span>
- [<span data-ttu-id="0e547-156">На борту устройств Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0e547-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="0e547-157">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="0e547-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="0e547-158">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="0e547-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="0e547-159">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="0e547-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="0e547-160">Запустите тест обнаружения на недавно созданных устройствах ATP Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e547-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="0e547-161">Устранение неполадок с бортовой защитой расширенных угроз Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e547-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)