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
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Подключение устройств Windows 10 с помощью средств управления мобильными устройствами

**Область применения:**

- [Предотвращение потери данных конечной точки Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Для настройки устройств можно использовать решения для управления мобильными устройствами (MDM). Microsoft 365 Endpoint data loss prevention supports MDM by providing OMA-URIs to create policies to manage devices.


## <a name="before-you-begin"></a>Перед началом работы
Если вы используете Microsoft Intune, необходимо зарегистрировать устройство MDM. В противном случае параметры не будут применены успешно. 

Дополнительные сведения о включив MDM с помощью Microsoft Intune, см. в регистрации устройств [(Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Ветвь устройств с помощью Microsoft Intune

Следуйте инструкциям из [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)

> [!NOTE]
> - Политика **"Состояние здоровья для устройств, на** которые вы на устройстве работает", использует свойства только для чтения и не может быть исправлена.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Отключение и мониторинг устройств с помощью средств управления мобильными устройствами

Из соображений безопасности срок действия пакета, используемой для отключенных устройств, истекает через 30 дней после даты его загрузки. Пакеты отключения с истекшим сроком действия, отправленные на устройство, будут отклонены. При скачии пакета отключения вы будете уведомлены о дате окончания срока действия пакетов, и он также будет включен в имя пакета.

> [!NOTE]
> Политики в отношении подключения и отключения не должны развертываться одновременно на одном устройстве, в противном случае это приведет к непредсказуемым столкновениям.

1. Получите пакет отключения из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)

2. В области навигации выберите **параметры** отключения устройства.  >    >  

3. В поле **"Метод развертывания"** выберите **"Управление мобильными устройствами/ Microsoft Intune".**
    
4. Щелкните **"Скачать пакет"** и сохраните ZIP-файл.

5. Извлеките содержимое ZIP-файла в общую папку, доступную только для чтения, доступную администраторам сети, которые будут развертывать пакет. У вас должен быть файл *с именем DeviceCompliance_valid_until_YYYY-MM-DD.offboarding.*

6. Используйте настраиваемую политику конфигурации Microsoft Intune для развертывания следующих поддерживаемых параметров OMA-URI.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Тип даты: String      
      Значение: [Скопируйте и включите значение из содержимого DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]

Дополнительные сведения о параметрах политики Microsoft Intune см. в параметрах политики [Windows 10 в Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> Политика **"Состояние состояния здоровья для отключенных устройств"** использует свойства только для чтения и не может быть исправлена.

> [!IMPORTANT]
> Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него есть, будут храниться до 6 месяцев.

## <a name="related-topics"></a>Связанные статьи
- [Ветвь устройств с Windows 10 с помощью групповой политики](dlp-configure-endpoints-gp.md)
- [Ветвь устройств с Windows 10 с помощью Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md)
- [Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](dlp-configure-endpoints-vdi.md)
- [Устранение неполадок с подсетями Advanced Threat Protection в Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
