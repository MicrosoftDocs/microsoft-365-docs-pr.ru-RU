---
title: Microsoft Defender для конечной точки на Android
ms.reviewer: ''
description: Описание установки и использования Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Android, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055105"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender для конечной точки на Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

В этом разделе описывается установка, настройка, обновление и использование Defender для конечной точки на Android.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечных точек наряду с Defender для конечной точки на Android может привести к проблемам с производительностью и непредсказуемым системным ошибкам.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Установка Microsoft Defender для конечной точки на Android

### <a name="prerequisites"></a>Предварительные требования

-   **Для конечных пользователей**

    -   Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения. См. [требования к microsoft Defender для лицензирования конечных точек](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Корпоративный портал Intune приложение можно загрузить из [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) и доступно на устройстве Android.

        -   Кроме того, устройство (s) можно записать через приложение Корпоративный портал Intune для применения политик соответствия требованиям устройств Intune. [](/mem/intune/user-help/enroll-device-android-company-portal) Это требует, чтобы конечному пользователю была назначена Microsoft Intune лицензия.

    -   Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Для администраторов**

    -   Доступ к порталу Центр безопасности в Microsoft Defender.

        > [!NOTE]
        > Microsoft Intune является единственным поддерживаемой системой управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки на Android. В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения политики соответствия требованиям Defender для конечной точки для Android, связанных с устройствами в Intune. 

    -   Доступ [Microsoft Endpoint Manager центра администрирования,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.
        
### <a name="network-requirements"></a>Требования к сети

- Чтобы Microsoft Defender для конечной точки на Android функционировал при подстройке к сети, необходимо настроить брандмауэр/прокси, чтобы включить доступ к URL-адресам службы Microsoft Defender для конечных [точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>Требования к системе

-   Мобильные телефоны под управлением Android 6.0 и выше. **Планшеты и другие мобильные устройства под управлением Android в настоящее время не поддерживаются.** 

-   Корпоративный портал Intune приложение загружается из [Google Play и](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) устанавливается. Регистрация устройств необходима для принудительного выполнения политик соответствия требованиям к устройствам Intune.

### <a name="installation-instructions"></a>Инструкции по установке

Microsoft Defender для конечной точки на Android поддерживает установку на обоих режимах зарегистрированных устройств — устаревших режимах администратора устройств Enterprise Android.
**В настоящее время в Android-Enterprise поддерживаются собственные устройства с профилем работы и полностью управляемыми пользовательскими устройствами корпоративной Enterprise. Поддержка других режимов Enterprise Android будет объявлена при готовности.**

Развертывание Microsoft Defender для конечной точки на Android Microsoft Intune (MDM).
Дополнительные сведения см. в [ссылке Развертывание Microsoft Defender для конечной точки на Android с Microsoft Intune](android-intune.md).


> [!NOTE]
> **Microsoft Defender для конечной точки на Android теперь доступен в [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> Вы можете подключиться к Google Play из Intune, чтобы развернуть приложение Microsoft Defender для конечных точек в режимах entrollment администратора устройств Enterprise Android. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Настройка Microsoft Defender для конечной точки на Android

Инструкции по настройке Microsoft Defender для конечной точки на Android доступны в [настройках Microsoft Defender для конечной](android-configure.md)точки на Android.



## <a name="related-topics"></a>Статьи по теме
- [Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune](android-intune.md)
- [Настройка функций Microsoft Defender для конечной точки на Android](android-configure.md)

