---
title: Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами
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
description: Используйте средства управления мобильными устройствами, чтобы развернуть пакет конфигурации на устройствах, чтобы они были подключены к службе.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769484"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="3fab5-103">Встроенные устройства с Windows 10 с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="3fab5-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="3fab5-104">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3fab5-104">**Applies to:**</span></span>

- [<span data-ttu-id="3fab5-105">Защита от потери данных (DLP) Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="3fab5-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="3fab5-106">Для настройки устройств можно использовать решения для управления мобильными устройствами (MDM).</span><span class="sxs-lookup"><span data-stu-id="3fab5-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="3fab5-107">Защита от потери данных в конечных точках Microsoft 365 поддерживает МДМС, предоставляя OMA-URIs для создания политик управления устройствами.</span><span class="sxs-lookup"><span data-stu-id="3fab5-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="3fab5-108">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="3fab5-108">Before you begin</span></span>
<span data-ttu-id="3fab5-109">Если вы используете Microsoft Intune, вам необходимо зарегистрировать устройство MDM.</span><span class="sxs-lookup"><span data-stu-id="3fab5-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="3fab5-110">В противном случае параметры не будут применены успешно.</span><span class="sxs-lookup"><span data-stu-id="3fab5-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="3fab5-111">Дополнительные сведения о включении MDM в Microsoft Intune содержатся в разделе [Регистрация устройств (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="3fab5-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="3fab5-112">Встроенные устройства с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3fab5-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="3fab5-113">Следуйте инструкциям в [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="3fab5-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="3fab5-114">Политика " **состояние работоспособности для встроенных устройств** " использует свойства, предназначенные только для чтения, и не может быть исправлено.</span><span class="sxs-lookup"><span data-stu-id="3fab5-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="3fab5-115">Переносе и мониторинг устройств с помощью средств управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="3fab5-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="3fab5-116">Из соображений безопасности для пакета, используемого для переносе устройств, срок действия истекает через 30 дней после загрузки даты.</span><span class="sxs-lookup"><span data-stu-id="3fab5-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="3fab5-117">Недействительные пакеты отключения, отправленные на устройство, будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="3fab5-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="3fab5-118">При загрузке пакета отключения вы получите уведомление об истечении срока действия пакетов, и оно также будет включено в имя пакета.</span><span class="sxs-lookup"><span data-stu-id="3fab5-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="3fab5-119">Входящая и исходящая политики не должны разворачиваться на одном устройстве одновременно, в противном случае это приведет к непредсказуемым конфликтам.</span><span class="sxs-lookup"><span data-stu-id="3fab5-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="3fab5-120">Получение пакета отключения от [центра соответствия требованиям корпорации Майкрософт](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3fab5-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="3fab5-121">В области навигации выберите **Параметры** отключение подключения  >  **устройства**  >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="3fab5-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="3fab5-122">В поле **метод развертывания** выберите **Управление мобильными устройствами/Microsoft Intune** .</span><span class="sxs-lookup"><span data-stu-id="3fab5-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune** .</span></span>
    
4. <span data-ttu-id="3fab5-123">Нажмите кнопку **загрузить пакет** и сохраните ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="3fab5-123">Click **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="3fab5-124">Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения и доступную для администраторов сети, которые будут развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="3fab5-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="3fab5-125">У вас должен быть файл с именем *DeviceCompliance_valid_until_YYYY – mm – dd.* отключаться.</span><span class="sxs-lookup"><span data-stu-id="3fab5-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* .</span></span>

6. <span data-ttu-id="3fab5-126">Используйте политику настраиваемой конфигурации Microsoft Intune, чтобы развернуть следующие поддерживаемые параметры OMA/URI.</span><span class="sxs-lookup"><span data-stu-id="3fab5-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="3fab5-127">OMA — URI:./девице/вендор/мсфт/виндовсадванцедсреатпротектион/оффбоардинг</span><span class="sxs-lookup"><span data-stu-id="3fab5-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="3fab5-128">Тип даты: строка</span><span class="sxs-lookup"><span data-stu-id="3fab5-128">Date type: String</span></span>      
      <span data-ttu-id="3fab5-129">Значение: [скопируйте и вставьте значение из содержимого файла DeviceCompliance_valid_until_YYYY – MM – DD. unof]</span><span class="sxs-lookup"><span data-stu-id="3fab5-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="3fab5-130">Дополнительные сведения о параметрах политики Microsoft Intune см. [в разделе Параметры политики Windows 10 в Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3fab5-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="3fab5-131">**Состояние работоспособности для политики устройств оффбоардед** использует свойства, предназначенные только для чтения, и не может быть исправлено.</span><span class="sxs-lookup"><span data-stu-id="3fab5-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fab5-132">Отключение останавливает отправку данных датчиков на портал, но данные с устройства, в том числе ссылки на все оповещения, которые она будет хранить, в течение 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="3fab5-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3fab5-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3fab5-133">Related topics</span></span>
- [<span data-ttu-id="3fab5-134">Встроенные устройства с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="3fab5-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="3fab5-135">Встроенные устройства с Windows 10 с помощью диспетчера конфигураций конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3fab5-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="3fab5-136">Встроенные устройства с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="3fab5-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="3fab5-137">Встроенные устройства неустойчивой инфраструктуры виртуальных рабочих столов (VDI)</span><span class="sxs-lookup"><span data-stu-id="3fab5-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="3fab5-138">Устранение неполадок, связанных с Advanced Threat Protection в защитнике Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3fab5-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
