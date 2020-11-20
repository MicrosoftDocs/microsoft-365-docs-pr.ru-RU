---
title: Регистрация устройств iOS/Ипадос и Android в тестовой среде Microsoft 365 для предприятий
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

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*

В этой статье описывается, как регистрировать и тестировать базовые возможности управления мобильными устройствами для устройств iOS/Ипадос и Android в тестовой среде Microsoft 365 для предприятий.

Регистрация устройств iOS/Ипадос и Android в тестовой среде состоит из трех этапов:
- [Этап 1: создание тестовой среды Microsoft 365 для предприятий](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2: регистрация устройств iOS/Ипадос и Android](#phase-2-enroll-your-ios-and-android-devices)
- [Этап 3: удаленное управление устройствами iOS и Ипадос и Android](#phase-3-manage-your-ios-and-android-devices-remotely)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1: создание тестовой среды Microsoft 365 для предприятий

Если вы хотите подать заявку на устройства iOS/Ипадос и Android в упрощенном виде с минимальными требованиями, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите зарегистрировать устройства iOS/Ипадос и Android на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS). Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное лицензирование и членство в группах, и вы можете поэкспериментировать с ним в среде, представляющей типичную организацию.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Этап 2: регистрация устройств с iOS и Android

Если вы просматриваете решение по управлению мобильными устройствами (MDM) для управления устройствами, вы можете использовать Microsoft Intune. При работе с каким бы то ни было поставщиком MDM, включая Intune, устройства "зарегистрированы". При регистрации они получают функции и параметры, которые вы настроили. 

В Intune существует несколько способов регистрации устройств iOS/Ипадос и Android. Вы можете выбрать вариант регистрации, который лучше всего подходит для вашей организации. Дополнительные сведения и рекомендации представлены в следующих статьях:

- [Руководство по развертыванию: регистрация устройств с iOS и Ипадос в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Руководство по развертыванию: регистрация устройств с Android в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Если вы готовы использовать Intune для управления устройствами и хотите получить некоторые рекомендации, то следующие сведения могут помочь:

- [Общие сведения об управлении устройствами](/mem/intune/fundamentals/what-is-device-management)
- [Руководство: пошаговое руководство Intune в диспетчере конечных точек Майкрософт](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Руководство по развертыванию: Настройка или переход в Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Этап 3: удаленное управление устройствами iOS и Android

Microsoft Intune обеспечивает функцию удаленной блокировки и сброса секретного кода. Если кто-то теряет свое устройство, вы можете удаленно заблокировать устройство. Если кто-то забыл свой секретный код, вы можете удаленно сбросить его.

- Чтобы удаленно заблокировать устройство iOS/Ипадос или Android, ознакомьтесь [со статьей Удаленная блокировка устройств с помощью Intune](/mem/intune/remote-actions/device-remote-lock).
- Чтобы удаленно сбросить секретный код, ознакомьтесь со статьей [Сброс или Удаление секретного кода устройства в Intune](/mem/intune/remote-actions/device-passcode-reset).

Дополнительные задачи, которые можно запускать удаленно, приведены в разделе [Доступные действия устройств](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Следующий шаг

Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)
  
[Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)
