---
title: ATP Защитника Майкрософт на iOS
ms.reviewer: ''
description: Описание установки и использования ATP Microsoft Defender для iOS
keywords: Microsoft, defender, atp, ios, overview, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: bc28c40443a6cae2815ad97126073df4579c494c
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768786"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender для конечной точки в iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender для конечной точки на iOS** будет предлагать защиту от фишинга и небезопасных сетевых подключений с веб-сайтов, электронной почты и приложений. Все оповещения будут доступны с помощью единой области стекла в Центре безопасности Защитника Майкрософт. Портал предоставляет группам безопасности централизованное представление угроз на устройствах iOS наряду с другими платформами.

> [!CAUTION]
> Запуск других сторонних продуктов защиты конечных точек наряду с Defender for Endpoint на iOS может привести к проблемам с производительностью и непредсказуемым системным ошибкам.

## <a name="pre-requisites"></a>Необходимые условия

**Для конечных пользователей**

- Лицензия Microsoft Defender для конечной точки, назначенная конечному пользователю приложения. См. требования к microsoft Defender для лицензирования [конечных точек.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- Device(s) [регистрироваться через](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) приложение Портал компании Intune для обеспечения соблюдения политик соответствия устройствам Intune. Это требует, чтобы конечному пользователю была назначена лицензия Microsoft Intune.
    - Приложение Портал компании Intune можно скачать из [Магазина приложений Apple.](https://apps.apple.com/us/app/intune-company-portal/id719171358)
    - Обратите внимание, что Apple не позволяет перенаправлять пользователей для скачивания других приложений из магазина приложений, и поэтому этот шаг должен быть сделан пользователем перед его загрузкой в приложение Microsoft Defender для конечной точки.

- Дополнительные сведения о назначении лицензий см. в дополнительных сведениях о назначении [лицензий пользователям.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

**Для администраторов**

- Доступ к порталу Центра безопасности Защитника Майкрософт.

    > [!NOTE]
    > Microsoft Intune — единственное поддерживаемое решение для управления мобильными устройствами (MDM) для развертывания Microsoft Defender для конечной точки в iOS. В настоящее время поддерживаются только зарегистрированные устройства для принудительного выполнения Defender для конечной точки в политиках соответствия требованиям к устройствам iOS в Intune.

- Доступ к [центру администрирования Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)чтобы развернуть приложение для зарегистрированных групп пользователей в вашей организации.

**Требования к системе**

- устройства iOS с iOS 11.0 и выше. Устройства iPad официально поддерживаются с версии 1.1.15010101 и дальше.

- Устройство регистрироваться с помощью [приложения Портал компании Intune.](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **AtP защитника Microsoft (Microsoft Defender для конечной точки) на iOS теперь доступен в [Магазине приложений Apple.](https://aka.ms/mdatpiosappstore)**

## <a name="installation-instructions"></a>Инструкции по установке

Развертывание конечной точки Microsoft Defender для iOS осуществляется с помощью Microsoft Intune (MDM), и поддерживаются как контролируемые, так и неконтролные устройства.
Дополнительные сведения см. в [сайте Deploy Microsoft Defender for Endpoint on iOS.](ios-install.md)

## <a name="resources"></a>Ресурсы

- Будьте в курсе предстоящих выпусков, посетив новые возможности [в Microsoft Defender для конечной](ios-whatsnew.md) точки на iOS или в нашем [блоге.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Предоставление обратной связи через систему обратной связи в приложении или через [портал SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Дальнейшие действия

- [Развертывание Microsoft Defender для конечной точки на iOS](ios-install.md)
- [Настройка Microsoft Defender для конечной точки для функций iOS](ios-configure-features.md)
