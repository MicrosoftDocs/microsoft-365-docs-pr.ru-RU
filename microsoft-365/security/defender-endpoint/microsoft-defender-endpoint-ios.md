---
title: Microsoft Defender для конечной точки в iOS
ms.reviewer: ''
description: Описание установки и использования Microsoft Defender для конечной точки на iOS
keywords: Microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3d9dd871edba29ec6119329f98ada990abad6e8d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246420"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender для конечной точки в iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender для конечной точки на iOS** будет предлагать защиту от фишинга и небезопасных сетевых подключений с веб-сайтов, электронной почты и приложений. Все оповещения будут доступны с помощью одной области стекла в Центр безопасности в Microsoft Defender. Портал предоставляет группам безопасности централизованное представление угроз на устройствах iOS наряду с другими платформами.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint на iOS может привести к проблемам с производительностью и непредсказуемым системным ошибкам.

## <a name="pre-requisites"></a>Необходимые условия

**Для конечных пользователей**

- Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения. См. требования к microsoft Defender для лицензирования [конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- Device(s) [регистрироваться](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) через приложение Корпоративный портал Intune для применения политик соответствия требованиям устройств Intune. Это требует, чтобы конечному пользователю была назначена Microsoft Intune лицензия.
    - Корпоративный портал Intune приложение можно скачать из [Магазина приложений Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Обратите внимание, что Apple не позволяет перенаправлять пользователей для скачивания других приложений из магазина приложений, и поэтому этот шаг должен быть сделан пользователем перед его загрузкой в приложение Microsoft Defender для конечной точки.

- Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Для администраторов**

- Доступ к порталу Центр безопасности в Microsoft Defender.

    > [!NOTE]
    > Microsoft Intune это единственное поддерживаемое решение управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки на iOS. В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения Defender для конечной точки в политиках соответствия требованиям к устройствам iOS в Intune.

- Доступ к [Microsoft Endpoint Manager центра администрирования,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.

**Требования к сети**
- Чтобы Microsoft Defender для конечной точки на iOS функционировала при подстройке к сети, необходимо настроить брандмауэр/прокси, чтобы включить доступ к URL-адресам [службы Microsoft Defender для конечных точек.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

**Требования к системе**

- устройства iOS с iOS 11.0 и выше. iPad официально поддерживается с версии 1.1.15010101.

- Устройство записуется с [приложением Корпоративный портал Intune.](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **ATP в Защитнике Microsoft (Microsoft Defender для конечной точки) на iOS теперь доступна в [Apple App Store.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Инструкции по установке

Развертывание Microsoft Defender для конечной точки на iOS осуществляется с Microsoft Intune (MDM), и поддерживаются как контролируемые, так и неконтролные устройства.
Дополнительные сведения см. в [сайте Deploy Microsoft Defender for Endpoint on iOS.](ios-install.md)

## <a name="resources"></a>Ресурсы

- Будьте в курсе предстоящих выпусков, посетив новые возможности [в Microsoft Defender для конечной](ios-whatsnew.md) точки на iOS или в нашем [блоге.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Предоставление обратной связи через систему обратной связи в приложении или через [портал SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Дальнейшие действия

- [Развертывание Microsoft Defender для конечной точки на iOS](ios-install.md)
- [Настройка Microsoft Defender для конечной точки для функций iOS](ios-configure-features.md)
