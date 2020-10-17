---
title: Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Используйте это руководство по лаборатории тестирования для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления ими.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487700"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*

В этой статье описывается, как регистрировать и тестировать базовые возможности управления мобильными устройствами для устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий.

Регистрация устройств iOS и Android в тестовой среде состоит из трех этапов:
- [Этап 1: создание тестовой среды Microsoft 365 для предприятий](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2: регистрация устройств с iOS и Android](#phase-2-enroll-your-ios-and-android-devices)
- [Этап 3: удаленное управление устройствами iOS и Android](#phase-3-manage-your-ios-and-android-devices-remotely)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1: создание тестовой среды Microsoft 365 для предприятий

Если вы хотите подать заявку на устройства iOS и Android в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите зарегистрировать устройства с iOS и Android на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS). Он предоставляется в качестве варианта, чтобы можно было протестировать автоматизированное лицензирование и членство в группах, и вы можете поэкспериментировать с ним в среде, представляющей типичную организацию.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Этап 2: регистрация устройств с iOS и Android

Сначала выполните инструкции в разделе [install и войдите в приложение корпоративного портала](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) , чтобы настроить приложение корпоративного портала Microsoft Intune для тестовой среды.

Затем воспользуйтесь инструкциями в статье [Настройка доступа к ресурсам компании](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , чтобы зарегистрировать устройство для iOS.

Затем используйте инструкции, приведенные в статье [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , чтобы зарегистрировать устройство с Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Этап 3: удаленное управление устройствами iOS и Android

Microsoft Intune предоставляет возможности удаленной блокировки и сброса секретного кода. Если кто-то теряет свое устройство, вы можете удаленно заблокировать устройство. Если кто-то забыл свой секретный код, вы можете удаленно сбросить его.
  
Чтобы удаленно заблокировать устройство iOS или Android, выполните указанные ниже действия.

1. Войдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) , используя учетные данные глобального администратора.
2. На портале Azure введите **Intune** в поле поиска, а затем выберите **Intune**.
3. Нажмите кнопку **устройства > все устройства**.
4. В списке устройств выберите устройство iOS или Android, а затем выберите действие **Remote Lock** .
    
Чтобы удаленно сбросить секретный код, выполните следующие действия.

1. При необходимости войдите на портал Azure по адресу, [https://portal.azure.com](https://portal.azure.com) используя учетные данные глобального администратора.
2. На портале Azure введите **Intune** в поле поиска, а затем выберите **Intune**.
3. Выберите **Devices**  >  **All Devices**(устройства).
4. В списке устройств, которыми вы управляете, выберите устройство для iOS или Android, выберите **... Дополнительно**, а затем выберите Удаленное действие **Удаление кода** для устройства.

Дополнительные эксперименты приведены в разделе [Доступные действия устройств](https://docs.microsoft.com/intune/device-management#available-device-actions).
    
## <a name="next-step"></a>Следующий этап

Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)
  
[Политики соответствия требованиям к устройствам для тестовой среды Microsoft 365 для предприятий](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)
