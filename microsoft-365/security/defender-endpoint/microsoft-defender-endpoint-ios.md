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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194857"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender для конечной точки в iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender для конечной точки на iOS** обеспечивает защиту от фишинга и небезопасных сетевых подключений с веб-сайтов, электронных почт и приложений. Все оповещения будут доступны с помощью одной области стекла в Центр безопасности в Microsoft Defender. Портал предоставляет группам безопасности централизованное представление угроз на устройствах iOS наряду с другими платформами.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint на iOS может привести к проблемам с производительностью и непредсказуемым системным ошибкам.

## <a name="pre-requisites"></a>Предварительные требования

**Для конечных пользователей**

- Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения. См. требования к microsoft Defender для лицензирования [конечных точек.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- **Для зарегистрированных устройств**: Device(s) региструются через приложение Корпоративный портал Intune для применения политик соответствия требованиям устройств Intune. [](/mem/intune/user-help/enroll-your-device-in-intune-ios) Это требует, чтобы конечному пользователю была назначена Microsoft Intune лицензия.
    - Корпоративный портал Intune приложение можно скачать из [Магазина приложений Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Обратите внимание, что Apple не позволяет перенаправлять пользователей для скачивания других приложений из магазина приложений, и поэтому этот шаг должен быть сделан пользователем перед его загрузкой в приложение Microsoft Defender для конечной точки.

- **Для незавершенных устройств**: Device(s) регистрируются с помощью Azure Active Directory. Это требует, чтобы конечный пользователь был подписан через [Microsoft Authenticator приложение](https://apps.apple.com/app/microsoft-authenticator/id983156458).

- Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Для администраторов**

- Доступ к порталу Центр безопасности в Microsoft Defender.

- Доступ к [Microsoft Endpoint Manager центра администрирования,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.

    > [!NOTE]
    > Microsoft Intune является единственным поддерживаемым решением единой конечной точки управления (UEM) для развертывания Microsoft Defender для конечной точки и принудительного обеспечения политики соответствия требованиям к устройствам, связанным с Endpoint, в Intune.

**Требования к системе**

- устройство iOS с iOS 11.0 и выше. iPad официально поддерживается с версии 1.1.15010101.

- Устройство регистрируется в приложении [Корпоративный портал Intune или](https://apps.apple.com/us/app/intune-company-portal/id719171358) регистрируется в Azure Active Directory через [Microsoft Authenticator.](https://apps.apple.com/app/microsoft-authenticator/id983156458)

## <a name="installation-instructions"></a>Инструкции по установке

Развертывание microsoft Defender для конечной точки на iOS можно сделать с помощью Microsoft Endpoint Manager (MEM), и поддерживаются как контролируемые, так и неподконтрольные устройства. Конечные пользователи также могут напрямую установить приложение из [магазина приложений Apple.](https://aka.ms/mdatpiosappstore)
Дополнительные сведения см. в [сайте Deploy Microsoft Defender for Endpoint on iOS.](ios-install.md)

## <a name="resources"></a>Ресурсы

- Будьте в курсе предстоящих выпусков, посетив новые возможности [в Microsoft Defender для конечной](ios-whatsnew.md) точки на iOS или в нашем [блоге.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Предоставление обратной связи через систему обратной связи в приложении или через [портал SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Дальнейшие действия

- [Развертывание Microsoft Defender для конечной точки на iOS](ios-install.md)
- [Настройка Microsoft Defender для конечной точки для функций iOS](ios-configure-features.md)
