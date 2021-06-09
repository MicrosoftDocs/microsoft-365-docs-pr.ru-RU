---
title: Регистрация устройств iOS/iPadOS и Android в Microsoft 365 для корпоративной тестовой среды
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Используйте это руководство по тестовой лаборатории для регистрации устройств в Microsoft 365 тестовой среде и удаленного управления ими.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367087"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Регистрация устройств iOS и Android в Microsoft 365 для корпоративной тестовой среды

*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

В этой статье описывается, как зарегистрироваться и протестировать базовые возможности управления мобильными устройствами для устройств iOS/iPadOS и Android в Microsoft 365 для корпоративной тестовой среды.

Регистрация устройств iOS/iPadOS и Android в тестовой среде включает три этапа:
- [Этап 1. Создание Microsoft 365 для корпоративной тестовой среды](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Регистрация устройств iOS/iPadOS и Android](#phase-2-enroll-your-ios-and-android-devices)
- [Этап 3. Управление устройствами iOS/iPadOS и Android удаленно](#phase-3-manage-your-ios-and-android-devices-remotely)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание Microsoft 365 для корпоративной тестовой среды

Если вы хотите легко зарегистрировать устройства iOS/iPadOS и Android с минимальными требованиями, следуйте инструкциям в базовой конфигурации [Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите записать устройства iOS/iPadOS и Android в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется смоделированная тестовая среда предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS). Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группах, а также экспериментировать с ним в среде, которая представляет собой типичную организацию.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Этап 2. Регистрация устройств с iOS и Android

Если вы рассматриваете решение управления мобильными устройствами (MDM) для управления устройствами, вы можете использовать Microsoft Intune. При работе с любым поставщиком MDM, включая Intune, устройства "зарегистрированы". При регистрации они получают настраиваемые функции и параметры. 

В Intune существует несколько способов регистрации устройств iOS/iPadOS и Android. Вы можете выбрать вариант регистрации, который лучше всего работает для вашей организации. Дополнительные сведения и рекомендации см. в следующих статьях:

- [Руководство по развертыванию: Регистрация устройств iOS и iPadOS в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Руководство по развертыванию: Регистрация устройств Android в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Если вы готовы использовать Intune для управления устройствами и хотите получить некоторые рекомендации, вам помогут следующие сведения:

- [Обзор управления устройствами](/mem/intune/fundamentals/what-is-device-management)
- [Учебник. Походить по intune в Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Руководство по развертыванию: настройка или перемещение в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Этап 3. Управление устройствами iOS и Android удаленно

Microsoft Intune предоставляет функцию удаленного сброса блокировки и пароля. Если кто-то теряет устройство, его можно удаленно заблокировать. Если кто-то забудет пароль, его можно удаленно сбросить.

- Чтобы удаленно заблокировать устройство iOS/iPadOS или Android, см. в примере [Remotely lock devices with Intune.](/mem/intune/remote-actions/device-remote-lock)
- Чтобы удаленно сбросить пароль, см. в перезагрузить или удалить пароль устройства [в Intune.](/mem/intune/remote-actions/device-passcode-reset)

Дополнительные задачи, которые можно выполнять удаленно, см. [в доступных действиях устройства.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>Следующий этап

Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#mobile-device-management) и возможностями управления мобильными устройствами в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)
  
[Политики соответствия требованиям к устройствам для Microsoft 365 для корпоративной тестовой среды](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)
