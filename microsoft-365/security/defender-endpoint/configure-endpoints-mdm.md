---
title: Подключение устройств Windows 10 с помощью средств управления мобильными устройствами
description: Используйте средства управления мобильными устройствами для развертывания пакета конфигурации на устройствах, чтобы они были размещены в службе.
keywords: бортовые устройства с использованием mdm, управления устройствами, на борту устройств Microsoft Defender для конечных точек, mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 951b0f33356ab99485f09ccc4147691e13ed3c6e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935009"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Подключение устройств Windows 10 с помощью средств управления мобильными устройствами

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Для настройки устройств можно использовать решения управления мобильными устройствами (MDM). Defender for Endpoint поддерживает MDM, OMA-URIs для создания политик для управления устройствами.

Дополнительные сведения об использовании CSP Defender для конечных точек см. в [CSP WindowsAdvancedThreatProtection и](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) [DDF WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)

## <a name="before-you-begin"></a>Прежде чем начать
Если вы используете Microsoft Intune, необходимо зарегистрироваться на устройстве MDM. В противном случае параметры не будут успешно применены. 

Дополнительные сведения о включаемом MDM в Microsoft Intune см. в записи [устройства (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Бортовые устройства с помощью Microsoft Intune

[![Изображение pdf-файлов с встроенными устройствами в Defender для конечной точки с помощью Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Ознакомьтесь с [PDF или](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) чтобы увидеть различные пути развертывания Defender для конечной точки. 

Следуйте инструкциям [из Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

Дополнительные сведения об использовании CSP Defender для конечных точек см. в [CSP WindowsAdvancedThreatProtection и](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) [DDF WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)


> [!NOTE]
> - Политика состояния здоровья для **бортовых устройств** использует свойства только для чтения и не может быть исправлена.
> - Конфигурация частоты отчетов о диагностических данных доступна только для устройств в Windows 10 версии 1703.


>[!TIP]
> После работы на устройстве можно выполнить тест обнаружения, чтобы убедиться, что устройство правильно вошел в службу. Дополнительные сведения см. в таблице Выполнить тест обнаружения на недавно созданном [устройстве Microsoft Defender для конечных точек.](run-detection-test.md)


Ознакомьтесь с [PDF или](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio,](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) чтобы увидеть различные пути развертывания Microsoft Defender для конечной точки.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard и мониторинг устройств с помощью средств управления мобильными устройствами
По соображениям безопасности срок действия пакета, используемой для устройств Offboard, истекает через 30 дней после даты его загрузки. Просроченные пакеты offboarding, отправленные на устройство, будут отклонены. При загрузке пакета offboarding вы будете уведомлены о дате истечения срока действия пакетов и он также будет включен в имя пакета.

> [!NOTE]
> На одном устройстве одновременно не следует развертывать политики бортового и оффбординга, в противном случае это приведет к непредсказуемым столкновениям.

1. Получите пакет offboarding из [Центра безопасности Защитника Майкрософт:](https://securitycenter.windows.com/)

   1. В области навигации выберите **Параметры**  >  **Offboarding**.

   1. Выберите Windows 10 в качестве операционной системы.

   1. В поле **Метод развертывания** выберите **управление мобильными устройствами / Microsoft Intune**.
    
   1. Нажмите **кнопку Скачать пакет** и сохраните файл .zip.

2. Извлеките содержимое файла .zip в общее расположение только для чтения, к которому можно получить доступ администраторов сети, которые будут развертывать пакет. Файл с именем *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding.*

3. Используйте настраиваемую политику конфигурации Microsoft Intune для развертывания следующих поддерживаемых ПАРАМЕТРОВ OMA-URI.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Тип даты: String<br/>
      Значение. [Скопируйте и включите значение из содержимого файла WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Дополнительные сведения о параметрах политики Microsoft Intune см. в [параметрах политики Windows 10 в Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)


> [!NOTE]
> Политика состояния здоровья для **отключенных** устройств использует свойства только для чтения и не может быть исправлена.

> [!IMPORTANT]
> Отключение приводит к тому, что устройство перестает отправлять данные датчиков на портал, но данные с устройства, включая ссылки на все оповещения, которые у него были, будут храниться до 6 месяцев.

## <a name="related-topics"></a>Похожие темы
- [На борту устройств Windows 10 с использованием групповой политики](configure-endpoints-gp.md)
- [На борту устройств Windows 10 с помощью Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Подключение устройств Windows 10 с помощью локального сценария](configure-endpoints-script.md)
- [Подключение временных устройств инфраструктуры виртуальных рабочих столов (VDI)](configure-endpoints-vdi.md)
- [Запустите тест обнаружения на недавно созданном устройстве Microsoft Defender для конечных точек](run-detection-test.md)
- [Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки](troubleshoot-onboarding.md)
