---
title: Регистрация устройств iOS, iPadOS и Android в тестовой среде Microsoft 365 для предприятий
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
description: Используйте это руководство по лаборатории тестирования для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления ими.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367087"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

В этой статье описывается регистрация и тестирование базовых возможностей управления мобильными устройствами для устройств iOS, iPadOS и Android в тестовой среде Microsoft 365 для предприятий.

Регистрация устройств iOS, iPadOS и Android в тестовой среде состоит из трех этапов:
- [Этап 1. Создание тестовой среды Microsoft 365 для предприятий](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Регистрация устройств с iOS, iPadOS и Android](#phase-2-enroll-your-ios-and-android-devices)
- [Этап 3. Удаленное управление устройствами с iOS, iPadOS и Android](#phase-3-manage-your-ios-and-android-devices-remotely)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание тестовой среды Microsoft 365 для предприятий

Если вы хотите зарегистрировать устройства с iOS, iPadOS и Android облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите зарегистрировать устройства с iOS, iPadOS и Android на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется тестовая среда имитированной организации, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS). Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать автоматическое лицензирование и членство в группах, а также поэкспериментировать с ним в среде, которая представляет типичную организацию.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Этап 2. Регистрация устройств с iOS и Android

Если вы рассматриваете решение для управления мобильными устройствами (MDM) для управления устройствами, вы можете использовать Microsoft Intune. При работе с любым поставщиком MDM, включая Intune, устройства "зарегистрированы". При регистрации они получают настраиваемые функции и параметры. 

В Intune существует несколько способов регистрации устройств с iOS, iPadOS и Android. Вы можете выбрать вариант регистрации, который лучше всего работает в вашей организации. Дополнительные сведения и рекомендации см. в следующих статьях:

- [Руководство по развертыванию: регистрация устройств iOS и iPadOS в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Руководство по развертыванию: регистрация устройств с Android в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Если вы готовы использовать Intune для управления устройствами и хотите получить некоторые рекомендации, вам могут помочь следующие сведения:

- [Обзор управления устройствами](/mem/intune/fundamentals/what-is-device-management)
- [Учебник: по walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Руководство по развертыванию: установка или переход на Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Этап 3. Удаленное управление устройствами с iOS и Android

Microsoft Intune предоставляет функцию удаленной блокировки и сброса пароля. Если кто-то потеряет свое устройство, вы можете удаленно заблокировать его. Если кто-то забудет свой пароль, вы можете удаленно сбросить его.

- Чтобы удаленно заблокировать устройство с iOS, iPadOS или Android, см. статью "Удаленная блокировка устройств [с помощью Intune".](/mem/intune/remote-actions/device-remote-lock)
- Чтобы удаленно сбросить пароль, см. ["Сброс" или "Удаление пароля устройства" в Intune.](/mem/intune/remote-actions/device-passcode-reset)

Дополнительные задачи, которые можно выполнять удаленно, [см. в доступных действиях с устройствами.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>Следующий этап

Изучите [дополнительные функции](m365-enterprise-test-lab-guides.md#mobile-device-management) и возможности управления мобильными устройствами в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)
  
[Политики соответствия устройств для тестовой среды Microsoft 365 для предприятий](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)
