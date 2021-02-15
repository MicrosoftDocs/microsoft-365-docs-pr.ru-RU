---
title: Политики соответствия устройств для тестовой среды Microsoft 365 для предприятий
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования, чтобы добавить политики соответствия устройств Intune в тестовую среду Microsoft 365 для предприятий.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367099"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Политики соответствия устройств для тестовой среды Microsoft 365 для предприятий

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

В этой статье описывается добавление политики соответствия устройств Intune для устройств с Windows 10 и приложений Microsoft 365 для предприятий в тестовую среду Microsoft 365 для предприятий.

Добавление политики соответствия устройств Intune состоит из двух этапов:
- [Этап 1. Создание тестовой среды Microsoft 365 для предприятий](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Создание политики соответствия устройств требованиям для устройств с Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание тестовой среды Microsoft 365 для предприятий

Если вы хотите настроить политики MAM только облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите настроить политики MAM на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS). Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать автоматическое лицензирование и членство в группах и поэкспериментировать с ним в типичной для организации среде.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Этап 2. Создание политики соответствия устройств требованиям для устройств с Windows 10

На этом этапе создается политика соответствия устройств требованиям для устройств с Windows 10. На этом этапе для добавления группы и создания политики соответствия требованиям используются Microsoft Intune и Центр администрирования [Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)

1. Перейдите в Центр администрирования [Microsoft 365](https://admin.microsoft.com)и войдите в свою подписку лаборатории тестирования Microsoft 365 с помощью учетной записи глобального администратора. Выберите Центр **администрирования Endpoint Manager.** Откроется [Центр администрирования Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)

    Если сообщение, аналогичное сообщению **"Вы** еще не включили управление устройствами", отображается, выберите Intune в качестве органа MDM. Конкретные действия см. в руководстве ["Настройка управления мобильными устройствами".](/mem/intune/fundamentals/mdm-authority-set)

    В Центре администрирования Endpoint Manager основное внимание уделяется управлению устройствами и приложениями. Чтобы узнать об этом Центре администрирования, см. руководство [по intune в Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. В **группах** добавьте новую группу **Microsoft 365** или security **с**  именем "Управляемые пользователи устройств с Windows **10"** с типом членства "Назначено". На следующих шагах вы назначите эту группу политику соответствия требованиям. 

    Конкретные действия, а также сведения о Microsoft  **365** или группах безопасности см. в подсети "Добавление групп для [организации пользователей и устройств".](/mem/intune/fundamentals/groups-add)

3. На **устройствах** создайте политику соответствия требованиям Windows 10. Назначьте эту политику созданной группе пользователей управляемых устройств **с Windows 10.**

    В политике можно блокировать простые пароли, требовать брандмауэр, требовать запуска службы защиты от взлома в Microsoft Defender и многого другое. Политика соответствия обычно включает базовые параметры или минимальный минимальный уровень, который должен быть у каждого устройства.

    Конкретные действия и сведения о доступных параметрах соответствия требованиям, которые можно настроить, см. в подстройке правил для управляемых вами устройств с помощью политик [соответствия](/mem/intune/protect/device-compliance-get-started)требованиям.

После завершения у вас будет политика соответствия устройств требованиям для тестирования участников в группе пользователей управляемых **устройств с Windows 10.**
  
## <a name="next-step"></a>Следующий этап

Изучите [дополнительные функции](m365-enterprise-test-lab-guides.md#mobile-device-management) и возможности управления мобильными устройствами в тестовой среде.

## <a name="see-also"></a>См. также

Руководства по лаборатории тестирования [Microsoft 365 для предприятий.](m365-enterprise-test-lab-guides.md)
  
[Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 для предприятий](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
