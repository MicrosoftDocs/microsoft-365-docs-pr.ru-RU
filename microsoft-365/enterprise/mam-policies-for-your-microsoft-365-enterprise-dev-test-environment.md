---
title: Политики соответствия требованиям к устройствам для Microsoft 365 для корпоративной тестовой среды
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
description: Используйте это руководство по тестовой лаборатории, чтобы добавить политики соответствия требованиям к устройствам Intune в Microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367099"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Политики соответствия требованиям к устройствам для Microsoft 365 для корпоративной тестовой среды

*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

В этой статье описывается, как добавить политику соответствия требованиям устройств Intune для Windows 10 устройств и Приложения Microsoft 365 для предприятий в Microsoft 365 для корпоративной тестовой среды.

Добавление политики соответствия требованиям устройств Intune включает два этапа:
- [Этап 1. Создание Microsoft 365 для корпоративной тестовой среды](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Этап 2. Создание политики соответствия требованиям устройств для Windows 10 устройств](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Этап 1. Создание Microsoft 365 для корпоративной тестовой среды

Если вы хотите настроить политики MAM только легким способом с минимальными требованиями, следуйте инструкциям в [легкой базовой конфигурации.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Если вы хотите настроить политики MAM в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется смоделированная тестовая среда предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса служб домена Active Directory (AD DS). Он предоставляется здесь в качестве параметра, чтобы можно было протестировать автоматическое лицензирование и членство в группе и поэкспериментировать с ним в среде, которая представляет собой типичную организацию.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Этап 2. Создание политики соответствия требованиям устройств для Windows 10 устройств

На этом этапе создается политика соответствия требованиям для Windows 10 устройств. На этом этапе Microsoft Intune и [центр администрирования Microsoft Endpoint Manager для](https://go.microsoft.com/fwlink/?linkid=2109431) добавления группы и создания политики соответствия требованиям.

1. Перейдите в [центр администрирования Microsoft 365](https://admin.microsoft.com)и войдите в свою Microsoft 365 тестовую лабораторную подписку с учетной записью глобального администратора. Выберите центр **Endpoint Manager** администратора. Открывается [Endpoint Manager центр](https://go.microsoft.com/fwlink/?linkid=2109431) администрирования.

    Если сообщение, аналогичное **you haven't enabled device management,** еще не отображается, выберите Intune в качестве органа MDM. Для определенных действий [см. в приложении Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).

    Центр администрирования Endpoint Manager фокусируется на управлении устройствами и управлении приложениями. Для экскурсии по этому центру администрирования [см. в учебнике: Walkthrough Intune в Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. В **Группах** добавьте новую группу **Microsoft 365** или группу безопасности с Windows 10 пользователями устройств **с** **присвоенным типом** членства.  На следующих действиях вы назначите эту группу политику соответствия требованиям. 

    Для определенных действий и сведений  о группах **Microsoft 365** или группах безопасности см. в добавлении групп [для организации пользователей и устройств.](/mem/intune/fundamentals/groups-add)

3. В **Устройствах** создайте политику Windows 10 соответствия требованиям. Назначьте эту политику группе **пользователей управляемых Windows 10 устройств,** созданной вами.

    В своей политике можно блокировать простые пароли, требовать брандмауэра, требовать запуска службы microsoft Defender Antimalware и других. Политика соответствия требованиям обычно включает базовые параметры или минимальный минимум, который должен иметь каждое устройство.

    Для определенных действий и сведений о доступных параметрах соответствия требованиям см. в статью Использование политик соответствия требованиям для установки правил для управляемых [устройств.](/mem/intune/protect/device-compliance-get-started)

По завершению у вас есть политика соответствия требованиям для устройств для тестирования участников в группе **Windows 10 пользователей устройств.**
  
## <a name="next-step"></a>Следующий этап

Ознакомьтесь [с дополнительными функциями](m365-enterprise-test-lab-guides.md#mobile-device-management) и возможностями управления мобильными устройствами в тестовой среде.

## <a name="see-also"></a>См. также

[Microsoft 365 для руководства лаборатории](m365-enterprise-test-lab-guides.md)тестирования предприятия .
  
[Регистрация устройств iOS и Android в Microsoft 365 для корпоративной тестовой среды](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
