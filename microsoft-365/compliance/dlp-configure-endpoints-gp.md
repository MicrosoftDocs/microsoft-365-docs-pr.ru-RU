---
title: Встроенные устройства с Windows 10 с помощью групповой политики
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
description: Используйте групповую политику для развертывания пакета конфигурации на устройствах с Windows 10, чтобы они были подключены к службе.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769449"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="f0e10-103">Встроенные устройства с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="f0e10-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="f0e10-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f0e10-104">**Applies to:**</span></span>

- [<span data-ttu-id="f0e10-105">Защита от потери данных (DLP) Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0e10-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="f0e10-106">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="f0e10-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="f0e10-107">Для развертывания пакета с помощью обновлений групповой политики (GP) необходимо находиться в Windows Server 2008 R2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="f0e10-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="f0e10-108">Для Windows Server 2019 может потребоваться замена NT Аусорити\велл-кновн-систем-аккаунт на NT AUTHORITY\SYSTEM файла XML, создаваемого предпочтением групповой политики.</span><span class="sxs-lookup"><span data-stu-id="f0e10-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="f0e10-109">Встроенные устройства с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="f0e10-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="f0e10-110">Откройте ZIP-файл пакета конфигурации GP ( *DeviceComplianceOnboardingPackage.zip* ), скачанный с помощью мастера входящей миграции служб.</span><span class="sxs-lookup"><span data-stu-id="f0e10-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="f0e10-111">Вы также можете получить пакет из [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="f0e10-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="f0e10-112">В области навигации выберите приподключение **Settings**  >  **устройства** параметров.</span><span class="sxs-lookup"><span data-stu-id="f0e10-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="f0e10-113">В поле **метод развертывания** выберите пункт **Групповая политика** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="f0e10-114">Нажмите кнопку **загрузить пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="f0e10-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="f0e10-115">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения и доступную для устройства.</span><span class="sxs-lookup"><span data-stu-id="f0e10-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="f0e10-116">Необходимо иметь папку с именем *оптионалпарамсполици* и файлом *девицекомплианцелокалонбоардингскрипт. cmd* .</span><span class="sxs-lookup"><span data-stu-id="f0e10-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="f0e10-117">Откройте [консоль управления групповыми политиками](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и выберите команду **изменить** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="f0e10-118">В **редакторе управления групповыми политиками** последовательно выберите **пункты Конфигурация компьютера** , **Параметры и** **Панель управления** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="f0e10-119">Щелкните правой кнопкой мыши пункт **Назначенные задания** , наведите указатель мыши на пункт **создать** и выберите пункт **немедленная задача (Windows 7 и более поздняя версия)** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="f0e10-120">В открывшемся окне **задачи** перейдите на вкладку **Общие** . В разделе **Параметры безопасности** щелкните **изменить пользователя или группу** и систему типов, а затем нажмите кнопку **Проверить имена** , а затем **ОК** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="f0e10-121">NT AUTHORITY\SYSTEM отображается в качестве учетной записи пользователя, от имени которой будет выполняться задача.</span><span class="sxs-lookup"><span data-stu-id="f0e10-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="f0e10-122">Выберите **выполнить, если пользователь вошел в систему, или нет** , установите флажок **запускать с наивысшими привилегиями** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="f0e10-123">Перейдите на вкладку **действия** и нажмите кнопку **создать...** Убедитесь, что в поле **действие** выбран пункт **Запуск программы** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="f0e10-124">Введите имя и расположение общего файла *виндовсдефендератпонбоардингскрипт. cmd* .</span><span class="sxs-lookup"><span data-stu-id="f0e10-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="f0e10-125">Нажмите кнопку **ОК** и закройте все открытые окна консоли управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="f0e10-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="f0e10-126">Устройства переносе с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="f0e10-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="f0e10-127">Из соображений безопасности для пакета, используемого для переносе устройств, срок действия истекает через 30 дней после загрузки даты.</span><span class="sxs-lookup"><span data-stu-id="f0e10-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="f0e10-128">Недействительные пакеты отключения, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="f0e10-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="f0e10-129">При загрузке пакета отключения вы получите уведомление об истечении срока действия пакетов, и оно также будет включено в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="f0e10-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e10-130">Входящая и исходящая политики не должны разворачиваться на одном устройстве одновременно, в противном случае это приведет к непредсказуемым конфликтам.</span><span class="sxs-lookup"><span data-stu-id="f0e10-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="f0e10-131">Получение пакета отключения от [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span><span class="sxs-lookup"><span data-stu-id="f0e10-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="f0e10-132">В области навигации выберите **Параметры**  >  **//девице** входящей миграции  >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="f0e10-133">В поле **метод развертывания** выберите пункт **Групповая политика** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="f0e10-134">Нажмите кнопку **загрузить пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="f0e10-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="f0e10-135">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения и доступную для устройства.</span><span class="sxs-lookup"><span data-stu-id="f0e10-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="f0e10-136">У вас должен быть файл с именем *DeviceComplianceOffboardingScript_valid_until_YYYY-мм-дд. cmd* .</span><span class="sxs-lookup"><span data-stu-id="f0e10-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="f0e10-137">Откройте [консоль управления групповыми политиками](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) , щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и выберите команду **изменить** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="f0e10-138">В **редакторе управления групповыми политиками** последовательно выберите **пункты Конфигурация компьютера,** **Параметры и** **Панель управления** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="f0e10-139">Щелкните правой кнопкой мыши пункт **Назначенные задания** , наведите указатель мыши на пункт **создать** и выберите пункт **немедленная задача** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="f0e10-140">В открывшемся окне **задачи** перейдите на вкладку **Общие** . Выберите учетную запись локального пользователя системы (БУИЛТИН\СИСТЕМ) в разделе **Параметры безопасности** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="f0e10-141">Выберите **выполнить, если пользователь вошел в систему или нет** , и установите флажок **запускать с наивысшими привилегиями** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="f0e10-142">Перейдите на вкладку **действия** и нажмите кнопку **создать..** .. Убедитесь, что в поле **действие** выбран пункт **Запуск программы** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="f0e10-143">Введите имя и расположение файла общего  *DeviceComplianceOffboardingScript_valid_until_YYYY-мм-дд. cmd* .</span><span class="sxs-lookup"><span data-stu-id="f0e10-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="f0e10-144">Нажмите кнопку **ОК** и закройте все открытые окна консоли управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="f0e10-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0e10-145">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства.</span><span class="sxs-lookup"><span data-stu-id="f0e10-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="f0e10-146">Мониторинг конфигурации устройства</span><span class="sxs-lookup"><span data-stu-id="f0e10-146">Monitor device configuration</span></span>
<span data-ttu-id="f0e10-147">С помощью групповой политики невозможно отслеживать развертывание политик на устройствах.</span><span class="sxs-lookup"><span data-stu-id="f0e10-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="f0e10-148">Мониторинг можно выполнить непосредственно на портале или с помощью различных средств развертывания.</span><span class="sxs-lookup"><span data-stu-id="f0e10-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="f0e10-149">Отслеживание устройств с помощью портала</span><span class="sxs-lookup"><span data-stu-id="f0e10-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="f0e10-150">Перейдите в [центр соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f0e10-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="f0e10-151">Щелкните список **устройств** .</span><span class="sxs-lookup"><span data-stu-id="f0e10-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="f0e10-152">Убедитесь, что устройства отображаются.</span><span class="sxs-lookup"><span data-stu-id="f0e10-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e10-153">Для начала показа устройств в **списке устройств** может потребоваться несколько дней.</span><span class="sxs-lookup"><span data-stu-id="f0e10-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="f0e10-154">Это включает время, необходимое для распространения политик на устройство, время, необходимое до входа пользователя в систему, а также время, необходимое для начала создания отчетов конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="f0e10-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f0e10-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f0e10-155">Related topics</span></span>
- [<span data-ttu-id="f0e10-156">Встроенные устройства с Windows 10 с помощью диспетчера конфигураций конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0e10-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="f0e10-157">Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="f0e10-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="f0e10-158">Встроенные устройства с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="f0e10-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="f0e10-159">Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="f0e10-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="f0e10-160">Запуск проверки обнаружения для новых подключенных устройств с защитником Майкрософт с пакетом ATP</span><span class="sxs-lookup"><span data-stu-id="f0e10-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="f0e10-161">Устранение неполадок, связанных с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0e10-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
