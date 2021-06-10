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
description: Используйте средства управления мобильными устройствами для развертывания пакета конфигурации на устройствах, чтобы они были размещены в службе.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917995"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="5c769-103">Подключение устройств Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5c769-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="5c769-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5c769-104">**Applies to:**</span></span>

- [<span data-ttu-id="5c769-105">Microsoft 365 Предотвращение потери конечных данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="5c769-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="5c769-106">Для настройки устройств можно использовать решения управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="5c769-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="5c769-107">Microsoft 365 Предотвращение потери данных конечной точки поддерживает MDM, OMA-URIs для создания политик для управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="5c769-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="5c769-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5c769-108">Before you begin</span></span>
<span data-ttu-id="5c769-109">Если вы используете Microsoft Intune, необходимо зарегистрироваться на устройстве MDM.</span><span class="sxs-lookup"><span data-stu-id="5c769-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="5c769-110">В противном случае параметры не будут успешно применены.</span><span class="sxs-lookup"><span data-stu-id="5c769-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="5c769-111">Дополнительные сведения о включаемом MDM с помощью Microsoft Intune см. в [Microsoft Intune.](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="5c769-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="5c769-112">На борту устройств с Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5c769-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="5c769-113">Следуйте инструкциям [из Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="5c769-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="5c769-114">Политика состояния здоровья для **бортовых устройств** использует свойства только для чтения и не может быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="5c769-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="5c769-115">Offboard и мониторинг устройств с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5c769-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="5c769-116">По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки.</span><span class="sxs-lookup"><span data-stu-id="5c769-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="5c769-117">Просроченные пакеты offboarding, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="5c769-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="5c769-118">При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="5c769-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="5c769-119">На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.</span><span class="sxs-lookup"><span data-stu-id="5c769-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="5c769-120">Получите пакет offboarding из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="5c769-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="5c769-121">В области навигации выберите **Параметры**  >  **устройства, включающее**  >  **offboarding.**</span><span class="sxs-lookup"><span data-stu-id="5c769-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="5c769-122">В поле **Метод развертывания** выберите **управление мобильными устройствами или Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="5c769-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="5c769-123">Щелкните **пакет Загрузка** и сохраните .zip файл.</span><span class="sxs-lookup"><span data-stu-id="5c769-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="5c769-124">Извлечение содержимого файла .zip в общее расположение только для чтения, к которому могут получить доступ сетевые администраторы, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="5c769-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="5c769-125">Файл с именем *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding.*</span><span class="sxs-lookup"><span data-stu-id="5c769-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="5c769-126">Используйте настраиваемую Microsoft Intune настройки для развертывания следующих поддерживаемых ПАРАМЕТРОВ OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="5c769-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="5c769-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="5c769-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="5c769-128">Тип даты: String</span><span class="sxs-lookup"><span data-stu-id="5c769-128">Date type: String</span></span>      
      <span data-ttu-id="5c769-129">Значение: [Скопируйте и включите значение из содержимого файла DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="5c769-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="5c769-130">Дополнительные сведения о параметрах политики Microsoft Intune см. в Windows 10 параметров политики [в Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="5c769-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="5c769-131">Политика состояния здоровья для **отключенных** устройств использует свойства только для чтения и не может быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="5c769-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c769-132">Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="5c769-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c769-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5c769-133">Related topics</span></span>
- [<span data-ttu-id="5c769-134">Onboard Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5c769-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="5c769-135">На борту Windows 10 устройства с Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5c769-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="5c769-136">Подключение устройств Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="5c769-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="5c769-137">Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="5c769-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="5c769-138">Устранение неполадок Расширенная защита от угроз в Microsoft Defender бортовых проблем</span><span class="sxs-lookup"><span data-stu-id="5c769-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)