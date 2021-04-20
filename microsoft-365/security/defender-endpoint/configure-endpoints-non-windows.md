---
title: Onboard non-Windows devices to the Microsoft Defender for Endpoint service
description: Настройте устройства без Windows, чтобы они могли отправлять данные датчиков в службу Microsoft Defender для конечных точек.
keywords: onboard non-Windows devices, macos, Linux, device management, configure Windows ATP devices, configure Microsoft Defender for Endpoint devices
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
ms.openlocfilehash: c78779cd4a8a329864b6ac7e0debfc30ca0b3a56
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893593"
---
# <a name="onboard-non-windows-devices"></a>Подключение устройствах, отличных от Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Платформы**
- macOS
- Linux

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender for Endpoint предоставляет централизованные операции безопасности как для Windows, так и для неконтроционных платформ. Вы сможете видеть оповещения из различных поддерживаемых операционных систем (ОС) в Центре безопасности Microsoft Defender и лучше защищать сеть организации. 

Вам необходимо знать точные версии дистрофии Linux и macOS, совместимые с Defender для конечной точки для работы интеграции. Дополнительные сведения см. в указанных ниже статьях.
- [Microsoft Defender для конечной точки в требованиях к системе Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Microsoft Defender для конечной точки в требованиях к системе macOS.](microsoft-defender-endpoint-mac.md#system-requirements)

## <a name="onboarding-non-windows-devices"></a>Onboarding non-Windows devices
Необходимо предпринять следующие действия на бортовых устройствах без Windows:
1. Выберите предпочтительный метод бортовой работы:

   - Для устройств macOS вы можете выбрать бортовой вариант через Microsoft Defender для конечной точки или через сторонное решение. Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки для Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - Для других устройств, не в том что касается Windows, выберите **onboard non-Windows devices через сторонную интеграцию.**   
    1. В области навигации выберите **Партнеров по интероперабельности.**  >   Убедитесь, что в списке находится сторонное решение.
    2. На **вкладке Приложения-партнеры** выберите партнера, поддерживаюного устройства, не в windows.
    3. Выберите **открытую страницу партнера,** чтобы открыть страницу партнера. Следуйте инструкциям, предоставленным на странице.
    4. После создания учетной записи или подписки на решение партнеров необходимо выйти на этап, когда клиенту Глобального администратора в организации будет предложено принять запрос на разрешение от партнерского приложения. Внимательно ознакомьтесь с запросом разрешений, чтобы убедиться, что он соответствует требуемой службе. 

        
2. Запустите тест обнаружения, следуя инструкциям сторонних решений.

## <a name="offboard-non-windows-devices"></a>Offboard non-Windows devices

1. Следуйте документации стороной, чтобы отключить сторонное решение от Microsoft Defender для конечной точки.

2. Удаление разрешений для сторонних решений в клиенте Azure AD.
   1. Войдите на [портал Azure](https://portal.azure.com).
   2. Выберите **Azure Active Directory > корпоративных приложений.**
   3. Выберите приложение, которое вы хотите отключить.
   4. Выберите **кнопку Удалить.**


## <a name="related-topics"></a>Похожие темы
- [Подключение устройств Windows 10](configure-endpoints.md)
- [Серверы на борту](configure-server-endpoints.md)
- [Настройка параметров прокси-сервера и соединения с Интернетом](configure-proxy-internet.md)
- [Устранение неполадок с учетом проблем с бортовой точкой Microsoft Defender для конечной точки](troubleshoot-onboarding.md)
