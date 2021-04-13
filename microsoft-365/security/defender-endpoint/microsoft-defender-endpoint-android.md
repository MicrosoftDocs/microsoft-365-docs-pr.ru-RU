---
title: ATP Защитника Майкрософт на Android
ms.reviewer: ''
description: Описание установки и использования ATP Microsoft Defender для Android
keywords: Microsoft, defender, atp, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 8311cb703bc5232e1421d19892fec9cdbc94b052
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698200"
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

### <a name="prerequisites"></a>Предварительные условия

-   **Для конечных пользователей**

    -   Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения. См. [требования к microsoft Defender для лицензирования конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Приложение Портала компании Intune можно скачать из [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) и доступно на устройстве Android.

        -   Кроме того, устройства(ы) могут быть зарегистрированы через приложение Портал компании Intune для применения политик соответствия требованиям устройств Intune. [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) Это требует, чтобы конечному пользователю была назначена лицензия Microsoft Intune.

    -   Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
        

-   **Для администраторов**

    -   Доступ к порталу Центра безопасности Защитника Майкрософт.

        > [!NOTE]
        > Microsoft Intune является единственным поддерживаемым решением управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки на Android. В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения политик соответствия требованиям Defender для конечной точки для Android, связанных с устройствами в Intune. 

    -   Доступ [к центру администрирования Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.

### <a name="system-requirements"></a>Требования к системе

-   Android-устройства под управлением Android 6.0 и выше.
-   Приложение портала компании Intune скачивается из [Google Play и](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) устанавливается. Регистрация устройств необходима для принудительного выполнения политик соответствия требованиям к устройствам Intune.

### <a name="installation-instructions"></a>Инструкции по установке

Microsoft Defender для конечной точки на Android поддерживает установку на обоих режимах зарегистрированных устройств — устаревших режимах администратора устройств и Android Enterprise.
**В настоящее время в Android Enterprise поддерживаются персональные устройства с профилем работы и полностью управляемыми пользовательскими устройствами. Поддержка других режимов Android Enterprise будет объявлена при готовности.**

Развертывание microsoft Defender для конечной точки на Android осуществляется с помощью Microsoft Intune (MDM).
Дополнительные сведения см. в [ссылке Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune.](android-intune.md)


> [!NOTE]
> **Microsoft Defender для конечной точки на Android теперь доступен в [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br> Вы можете подключиться к Google Play из Intune для развертывания приложения Microsoft Defender для конечных точек в режимах entrollment администратора устройств и Android Enterprise. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Настройка Microsoft Defender для конечной точки на Android

Инструкции по настройке Microsoft Defender для конечной точки на Android доступны в [настройках Microsoft Defender для конечной](android-configure.md)точки на Android.



## <a name="related-topics"></a>Статьи по теме
- [Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune](android-intune.md)
- [Настройка Microsoft Defender для конечной точки на android-функции](android-configure.md)

