---
title: Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Используйте это руководство по лаборатории тестирования для регистрации устройств в тестовой среде Microsoft 365 и удаленного управления ими.
ms.openlocfilehash: e653b3e6cafb6ee2eb492709a2d060c7b92a6904
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281256"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Регистрация устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise

Следуя инструкциям, приведенным в этой статье, вы сможете регистрировать и тестировать базовые возможности управления мобильными устройствами для устройств с iOS и Android в тестовой среде Microsoft 365 Enterprise.

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Этап 1: создание тестовой среды Microsoft 365 Enterprise

Если вы хотите, чтобы вы просто зарегистрировали устройства iOS и Android в упрощенном виде с минимальными требованиями, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите зарегистрировать устройства с iOS и Android на имитации предприятия, следуйте инструкциям в сквозной [проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.
  
> [!NOTE]
> Для тестирования автоматического лицензирования и членства в группах не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS). Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Этап 2: регистрация устройств с iOS и Android

Сначала выполните инструкции в разделе [install и войдите в приложение корпоративного портала](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) , чтобы настроить приложение корпоративного портала Microsoft Intune для тестовой среды.

Затем воспользуйтесь инструкциями в статье [Настройка доступа к ресурсам компании](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , чтобы зарегистрировать устройство для iOS.

Затем используйте инструкции, приведенные в статье [Регистрация устройства Android в Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , чтобы зарегистрировать устройство с Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Этап 3: удаленное управление устройствами iOS и Android

Microsoft Intune предоставляет возможности удаленной блокировки и сброса секретного кода. Если пользователь потеряет свое устройство, вы можете заблокировать это устройство удаленно. Если кто-то забыл свой секретный код, его можно сбросить в удаленном режиме.
  
Чтобы удаленно заблокировать устройство iOS или Android:

1. Войдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) , используя учетные данные глобального администратора.
2. Выберите **все службы**, введите **Intune**, а затем щелкните **Intune**.
3. Нажмите кнопку **Devices _Гт_ All Devices (устройства**).
4. В списке устройств выберите устройство iOS или Android, а затем щелкните действие **Remote Lock** .

    
Чтобы удаленно сбросить секретный код, сделайте следующее:

1. При необходимости войдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com) , используя учетные данные глобального администратора.
2. Выберите **все службы**, введите **Intune**, а затем щелкните **Intune**.
3. Нажмите кнопку **Devices _Гт_ All Devices (устройства**).
4. В списке управляемых устройств щелкните устройство iOS или Android и выберите **... Дополнительные сведения**. Затем выберите Удаленное действие **удалить секретный код** устройства.

Дополнительные эксперименты приведены в разделе [Доступные действия устройств](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Следующее действие

Узнайте о дополнительных возможностях и возможностях [управления мобильными устройствами](m365-enterprise-test-lab-guides.md#mobile-device-management) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)
  
[Политики соответствия требованиям устройств для тестовой среды Microsoft 365 корпоративный](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
