---
title: Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: В этом документе Test Lab Guide используйте для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870576"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 корпоративный

Выполнив инструкции, приведенные в этой статье, вы сможете регистрация и проверка возможности управления базовой мобильного устройства для iOS и Android в тестовой среде Microsoft 365 для предприятия.

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия

Если необходимо зарегистрировать iOS и Android в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если необходимо зарегистрировать iOS и Android в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Тестирование автоматизирована лицензирования и членства в группе не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверка автоматической лицензирования и членство в группах и экспериментировать с его в среде, которая представляет типичное организации. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Этап 2: Регистрация операций ввода-вывода и Android

Во-первых, используйте инструкции в [установки и войдите в приложение портала компании](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) для настройки приложения портала компании Майкрософт Intune для тестовой среды.

Затем используйте инструкции из статьи [Настройка доступа к ресурсам компании](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) для подачи заявок на устройстве операций ввода-вывода.

Затем используйте инструкции из статьи [Заявка Android устройство в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) возможность зачисления Android устройства.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Этап 3: IOS и Android удаленного управления

Microsoft Intune предоставляет удаленного блокировки и код связи для сброса возможности. Если кто-то теряет свои устройства, можно заблокировать устройство удаленно. Если кто-то забудет их код связи, ее можно восстановить удаленно.
  
Чтобы заблокировать операций ввода-вывода или Android устройство удаленно:

1. Войдите в портал Azure в [https://portal.azure.com](https://portal.azure.com) с использованием учетных данных учетной записи глобального администратора.
2. Выберите **все службы**, введите **Intune**и нажмите кнопку **Intune**.
3. Нажмите кнопку **устройства > все устройства**.
4. В списке устройств нажмите кнопку операций ввода-вывода или Android устройства и нажмите кнопку действие **удаленного блокировки** .

    
Чтобы удаленно сбросить секретный код, сделайте следующее:

1. При необходимости, войдите в портал Azure в [https://portal.azure.com](https://portal.azure.com) с использованием учетных данных учетной записи глобального администратора.
2. Выберите **все службы**, введите **Intune**и нажмите кнопку **Intune**.
3. Нажмите кнопку **устройства > все устройства**.
4. В списке устройств, управление, щелкните операций ввода-вывода или Android устройство и выберите **... Дополнительные**. Выберите действие удаленных устройств **Удалить секретный код** .

Дополнительные экспериментов в разделе [действия из доступных устройств](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Следующее действие

Изучите дополнительное [Управление мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) функций и возможностей в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)
  
[Политики MAM для вашей тестовой среды Microsoft 365 корпоративный](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Мобильные решения на предприятиях + безопасности (Командной)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
