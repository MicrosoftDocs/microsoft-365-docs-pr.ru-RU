---
title: Подключение устройств Windows 10 с помощью средств управления мобильными устройствами
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
description: Используйте средства управления мобильными устройствами для развертывания пакета конфигурации на устройствах, чтобы они были доступны в службе.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769484"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="bb129-103">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="bb129-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="bb129-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bb129-104">**Applies to:**</span></span>

- [<span data-ttu-id="bb129-105">Предотвращение потери данных конечной точки Microsoft 365 (DLP)</span><span class="sxs-lookup"><span data-stu-id="bb129-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="bb129-106">Для настройки устройств можно использовать решения для управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="bb129-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="bb129-107">Microsoft 365 Endpoint data loss prevention supports MDM by providing OMA-URIs to create policies to manage devices.</span><span class="sxs-lookup"><span data-stu-id="bb129-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="bb129-108">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bb129-108">Before you begin</span></span>
<span data-ttu-id="bb129-109">Если вы используете Microsoft Intune, необходимо зарегистрировать устройство MDM.</span><span class="sxs-lookup"><span data-stu-id="bb129-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="bb129-110">В противном случае параметры не будут применены успешно.</span><span class="sxs-lookup"><span data-stu-id="bb129-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="bb129-111">Дополнительные сведения о включив MDM с помощью Microsoft Intune, см. в регистрации устройств [(Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="bb129-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="bb129-112">Ветвь устройств с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bb129-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="bb129-113">Следуйте инструкциям из [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="bb129-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="bb129-114">Политика **"Состояние здоровья для устройств, на** которые вы на устройстве работает", использует свойства только для чтения и не может быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="bb129-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="bb129-115">Отключение и мониторинг устройств с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="bb129-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="bb129-116">Из соображений безопасности срок действия пакета, используемой для отключенных устройств, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="bb129-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="bb129-117">Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="bb129-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="bb129-118">При скачии пакета отключения вы будете уведомлены о дате окончания срока действия пакетов, и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="bb129-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="bb129-119">Политики в отношении подключения и отключения не должны развертываться одновременно на одном устройстве, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="bb129-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="bb129-120">Получите пакет отключения из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="bb129-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="bb129-121">В области навигации выберите **параметры** отключения устройства.  >    >  </span><span class="sxs-lookup"><span data-stu-id="bb129-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="bb129-122">В поле **"Метод развертывания"** выберите **"Управление мобильными устройствами/ Microsoft Intune".**</span><span class="sxs-lookup"><span data-stu-id="bb129-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="bb129-123">Щелкните **"Скачать пакет"** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="bb129-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="bb129-124">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную администраторам сети, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="bb129-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="bb129-125">У вас должен быть файл *с именем DeviceCompliance_valid_until_YYYY-MM-DD.offboarding.*</span><span class="sxs-lookup"><span data-stu-id="bb129-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="bb129-126">Используйте настраиваемую политику конфигурации Microsoft Intune для развертывания следующих поддерживаемых параметров OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="bb129-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="bb129-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="bb129-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="bb129-128">Тип даты: String</span><span class="sxs-lookup"><span data-stu-id="bb129-128">Date type: String</span></span>      
      <span data-ttu-id="bb129-129">Значение: [Скопируйте и включите значение из содержимого DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span><span class="sxs-lookup"><span data-stu-id="bb129-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="bb129-130">Дополнительные сведения о параметрах политики Microsoft Intune см. в параметрах политики [Windows 10 в Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="bb129-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="bb129-131">Политика **"Состояние состояния здоровья для отключенных устройств"** использует свойства только для чтения и не может быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="bb129-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb129-132">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него есть, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="bb129-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb129-133">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="bb129-133">Related topics</span></span>
- [<span data-ttu-id="bb129-134">Ветвь устройств с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="bb129-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="bb129-135">Ветвь устройств с Windows 10 с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bb129-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="bb129-136">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="bb129-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="bb129-137">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="bb129-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="bb129-138">Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bb129-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
