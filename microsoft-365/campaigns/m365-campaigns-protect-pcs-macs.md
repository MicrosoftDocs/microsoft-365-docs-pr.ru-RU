---
title: Защита неуправляемых компьютеров с Windows 10 и компьютеров Mac
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
ms.openlocfilehash: 40e94e2f961ab34827de4ce5e43e100af53a7340
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227503"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Защита неуправляемых компьютеров с Windows 10 и компьютеров Mac

Вы можете управлять Windows 10 компьютерами и компьютерами Mac, зачислив их в Microsoft Intune, что позволяет убедиться, что они здоровы и безопасны перед доступом к данным в вашей среде. Однако многие кампании и малые предприятия включают сотрудников, которые приносят свои собственные устройства (BYOD), которые не будут управляться организацией. Для этих неугомонных компьютеров и компьютеров Mac используйте эту статью, чтобы обеспечить настройку минимальных возможностей безопасности.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Защита компьютера с Windows 10 mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Если Windows 10 или Mac не управляется вашей организацией, не забудьте настроить эти возможности безопасности.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Включив шифрование устройств**<p>

Шифрование устройств доступно на широком диапазоне устройств Windows и помогает защитить данные, шифруя их. Если включить шифрование устройств, доступ к вашему устройству и данным смогут получить только уполномоченные лица. [Включаем шифрование](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) устройств для инструкций.

 Если шифрование устройства не доступно на устройстве, вместо этого можно включить стандартное [шифрование BitLocker.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) (BitLocker не доступен в Windows 10 Домашняя выпуске.) 

**Защитите устройство с помощью Безопасность Windows**<p>
Если у вас Windows 10, вы получите последнюю антивирусную защиту с помощью Безопасность Windows. При первом запуске Windows 10, Безопасность Windows активно помогает защитить компьютер, сканируя вредоносные программы(вредоносные программы), вирусы и угрозы безопасности. Безопасность Windows защиты в режиме реального времени для сканирования всего, что вы скачиваете или работаете на компьютере.

Центр обновления Windows автоматически скачивает обновления для приложения "Безопасность Windows", чтобы обеспечить безопасность вашего компьютера и защитить его от угроз.

Если у вас есть более раная версия Windows и используется Microsoft Security Essentials, лучше перейти к Безопасность Windows. Дополнительные сведения см. [в справке о защите устройства с помощью Безопасность Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Включаем Windows брандмауэр**<p>
Вы всегда должны запускать Windows брандмауэра, даже если включен другой брандмауэр. Отключение Windows брандмауэра может сделать ваше устройство (и сеть, если у вас есть) более уязвимым для несанкционированного доступа. См. [Windows брандмауэра](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) включить или отключить для инструкций.

## <a name="mac"></a>[Mac](#tab/Mac)

**Используйте FileVault для шифрования диска Mac**<p>
Шифрование диска защищает данные в случае потери или кражи устройств. Шифрование полного диска FileVault помогает предотвратить несанкционированный доступ к данным на вашем диске запуска. См. [в инструкциях с помощью FileVault](https://support.apple.com/HT204837) для шифрования диска запуска на Mac.

**Защита mac от вредоносных программ**<p>
Корпорация Майкрософт рекомендует установить и использовать надежное антивирусное программное обеспечение на Компьютере Mac. Список вариантов: Лучший антивирус [Mac 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)см. в следующей статье.

Вы также можете снизить риск вредоносных программ, используя программное обеспечение только из надежных источников. Параметры в параметрах & конфиденциальности позволяют указать источники программного обеспечения, установленного на Mac. Дополнительные сведения см. в [дополнительных сведениях о защите Mac от вредоносных программ.](https://support.apple.com/kb/PH25087)

**Включить защиту брандмауэра**<p>
Используйте параметры брандмауэра, чтобы защитить Mac от нежелательного контакта, инициированного другими компьютерами, когда вы подключены к Интернету или сети. Без этой защиты mac может быть более уязвимым для несанкционированного доступа. Узнайте [о брандмауэре приложений](https://support.apple.com/HT201642) для инструкций.
