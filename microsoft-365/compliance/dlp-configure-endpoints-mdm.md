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
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Подключение устройств Windows 10 с помощью средств управления мобильными устройствами

**Область применения:**

- [Предотвращение потери данных конечной точки Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)

Для настройки устройств можно использовать решения управления мобильными устройствами (MDM). Microsoft 365 Endpoint data loss prevention supports MDM by providing OMA-URIs to create policies to manage devices.


## <a name="before-you-begin"></a>Подготовка
Если вы используете Microsoft Intune, необходимо зарегистрироваться на устройстве MDM. В противном случае параметры не будут успешно применены. 

Дополнительные сведения о включаемом MDM в Microsoft Intune см. в записи [устройства (Microsoft Intune).](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Бортовые устройства с помощью Microsoft Intune

Следуйте инструкциям [из Intune](/intune/advanced-threat-protection).

> [!NOTE]
> - Политика состояния здоровья для **бортовых устройств** использует свойства только для чтения и не может быть исправлена.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard и мониторинг устройств с помощью средств управления мобильными устройствами

По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки. Просроченные пакеты offboarding, отправленные на устройство, будут отклонены. При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.

> [!NOTE]
> На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.

1. Получите пакет offboarding из [Центра соответствия требованиям Майкрософт.](https://compliance.microsoft.com/)

2. В области навигации выберите **устройство Параметры,**  >  **включающее**  >  **offboarding.**

3. В поле **Метод развертывания** выберите **управление мобильными устройствами / Microsoft Intune**.
    
4. Нажмите **кнопку Скачать пакет** и сохраните файл .zip.

5. Извлеките содержимое файла .zip в общее расположение только для чтения, к которому можно получить доступ администраторов сети, которые будут развертывать пакет. Файл с именем *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding.*

6. Используйте настраиваемую политику конфигурации Microsoft Intune для развертывания следующих поддерживаемых ПАРАМЕТРОВ OMA-URI.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Тип даты: String      
      Значение: [Скопируйте и включите значение из содержимого файла DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Дополнительные сведения о параметрах политики Microsoft Intune см. в [параметрах политики Windows 10 в Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> Политика состояния здоровья для **отключенных** устройств использует свойства только для чтения и не может быть исправлена.

> [!IMPORTANT]
> Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.

## <a name="related-topics"></a>Связанные статьи
- [На борту устройств Windows 10 с использованием групповой политики](dlp-configure-endpoints-gp.md)
- [На борту устройств Windows 10 с помощью Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](dlp-configure-endpoints-script.md)
- [Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](dlp-configure-endpoints-vdi.md)
- [Устранение неполадок с бортовой защитой расширенных угроз Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)