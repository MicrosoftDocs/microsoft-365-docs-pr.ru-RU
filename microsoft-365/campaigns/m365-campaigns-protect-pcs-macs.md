---
title: Защита неуправляемых компьютеров с Windows 10 и компьютеров Mac
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Защита неугодных или собственных устройств (BYOD) с помощью Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044388"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Защита неуправляемых компьютеров с Windows 10 и компьютеров Mac

Вы можете управлять компьютерами с Windows 10 и Компьютерами Mac, зарегистрировав их в Microsoft Intune, что позволяет убедиться, что они безопасны и безопасны перед доступом к данным в вашей среде. Однако многие кампании и малые предприятия включают сотрудников, которые работают с собственными устройствами (BYOD), которыми не управляет организация. Для таких неугодных компьютеров и компьютеров Mac воспользуйтесь этой статьей, чтобы убедиться, что настроены минимальные возможности безопасности.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Защита компьютера под управлением Windows 10 или Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Если компьютер с Windows 10 или Mac не управляется вашей организацией, настройте эти возможности безопасности.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Включить шифрование устройства**<p>

Шифрование устройств доступно на широком спектре устройств с Windows и помогает защитить ваши данные, шифруя их. Если включить шифрование устройства, только авторизованные лица смогут получить доступ к вашему устройству и данным. Инструкции [см.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) в инструкциях по включению шифрования устройства.

 Если шифрование устройства не доступно на вашем устройстве, вы можете включить стандартное шифрование [BitLocker.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) (BitLocker не доступен в windows 10 Домашняя.) 

**Защита устройства с помощью системы безопасности Windows**<p>
Если у вас есть Windows 10, вы получите последнюю антивирусную защиту с помощью Windows Security. При первом запуске Windows 10 система безопасности Windows активна и активно помогает защитить компьютер, сканируя вредоносные программы (вредоносные программы), вирусы и угрозы безопасности. Система безопасности Windows использует защиту в режиме реального времени для сканирования всех загружаемых или запускаемых данных на компьютере.

Центр обновления Windows автоматически скачивает обновления для приложения "Безопасность Windows", чтобы обеспечить безопасность вашего компьютера и защитить его от угроз.

Если у вас есть более ранная версия Windows и вы используете Microsoft Security Essentials, то лучше перейти на windows Security. Дополнительные сведения см. в [справке по защите устройства с помощью Windows Security.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Включить брандмауэр Windows**<p>
Следует всегда запускать брандмауэр Windows, даже если включен другой брандмауэр. Отключение брандмауэра Windows может сделать устройство (и сеть, если он у вас есть) более уязвимыми для несанкционированного доступа. Инструкции [см.](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) в инструкциях по включению и отключению брандмауэра Windows

## <a name="mac"></a>[Mac](#tab/Mac)

**Шифрование диска Mac с помощью FileVault**<p>
Шифрование диска защищает данные при утере или краже устройств. Шифрование на полном диске FileVault помогает предотвратить несанкционированный доступ к информации на диске запуска. Инструкции см. в инструкциях по шифрованию диска запуска на компьютере Mac с помощью [FileVault.](https://support.apple.com/HT204837)

**Защита mac от вредоносных программ**<p>
Корпорация Майкрософт рекомендует устанавливать и использовать надежное антивирусное ПО на компьютере Mac. Список вариантов: лучшая антивирусная программа [для Mac 2019: ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)см. в следующей статье.

Вы также можете снизить риск вредоносного ПО, используя программное обеспечение только из надежных источников. Параметры в параметрах & конфиденциальности позволяют указать источники программного обеспечения, установленного на компьютере Mac. Дополнительные сведения см. в [этой теме, чтобы защитить Компьютер Mac от вредоносных программ.](https://support.apple.com/kb/PH25087)

**Включить защиту брандмауэра**<p>
Используйте параметры брандмауэра, чтобы защитить компьютер Mac от нежелательных контактов, инициированных другими компьютерами при подсети или к Интернету. Без этой защиты компьютер Mac может быть более уязвимым к несанкционированному доступу. Инструкции [см. в брандмауэре](https://support.apple.com/HT201642) приложений.
