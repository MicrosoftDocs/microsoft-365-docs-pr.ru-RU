---
title: Защитите неуправляемые компьютеры с Windows 10 и Mac
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Защита от фишинга и других атак с помощью Microsoft 365 для кампаний.
ms.openlocfilehash: 93bb36f115ee5f83e07ac9623c852fec4dbf205f
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753628"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Защитите неуправляемые компьютеры с Windows 10 и Mac

Вы можете управлять компьютерами с Windows 10 и Макинтошми, заменяя их в Microsoft Intune, что позволяет убедиться, что они работоспособны и безопасны, прежде чем получать доступ к данным в вашей среде. Однако многие кампании и малые предприятия включают сотрудников, которые приносят свои собственные устройства (BYOD), которые не будут управляться Организацией. Для этих неуправляемых компьютеров и компьютеров Макинтош используйте эту статью, чтобы убедиться в том, что минимальные возможности безопасности настроены. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Защита компьютера под управлением Windows 10 или Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Если ваш компьютер с Windows 10 или Mac не управляется вашей организацией, обязательно настройте эти функции безопасности.

## <a name="windows-10tabwindows10"></a>[Windows 10](#tab/Windows10)
**Включение шифрования устройств**<p>

Шифрование устройств доступно для широкого спектра устройств Windows и защищает данные путем их шифрования. Если включено шифрование устройства, только авторизованные пользователи смогут получать доступ к устройству и данным. Инструкции по [включению шифрования устройств](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .

 Если шифрование устройства недоступно на вашем устройстве, вместо этого можно включить стандартное [Шифрование BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) . (BitLocker недоступен в Windows 10 Home Edition.) 


**Защита устройства с помощью системы безопасности Windows**<p>
Если у вас есть Windows 10, вы получите последнюю антивирусную защиту с помощью системы безопасности Windows. При первом запуске Windows 10 система безопасности Windows включена и активно помогает защитить компьютер, проверяя наличие вредоносных программ, вирусов и угроз безопасности. Система безопасности Windows использует защиту в режиме реального времени для сканирования всех загружаемых или выполняемых на компьютере компонентов.

Центр обновления Windows автоматически загружает обновления для безопасности Windows, чтобы защитить компьютер и защитить его от угроз.

Если вы используете более раннюю версию Windows и используете Microsoft Security Essentials, рекомендуется переместиться в систему безопасности Windows. Дополнительные сведения можно найти в статье [Защита устройства с помощью безопасности Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Включение брандмауэра Windows**<p>
Следует всегда запускать брандмауэр Windows, даже если включен другой брандмауэр. Отключение брандмауэра Windows может сделать устройство (и сеть, если она есть) более уязвимым для несанкционированного доступа. Инструкции по [включению и отключению брандмауэра Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mactabmac"></a>[Mac](#tab/Mac)
**Использование Филеваулт для шифрования диска Mac**<p>
Шифрование диска защищает данные в случае потери или кражи устройств. Филеваулт полное шифрование диска предотвращает несанкционированный доступ к информации на загрузочном диске. [В разделе Использование филеваулт для шифрования загрузочного диска в Mac](https://support.apple.com/HT204837) .

**Защита Макинтош от вредоносных программ**<p>
Корпорация Майкрософт рекомендует установить и использовать надежное антивирусное программное обеспечение на компьютере Mac. В следующей статье приведен список вариантов: лучшая версия для [Macintosh antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Кроме того, вы можете снизить риск заражения вредоносными программами, используя программное обеспечение только из надежных источников. Параметры в параметрах безопасности & конфиденциальности позволяют указать источники программного обеспечения, установленные на компьютере Mac. Дополнительные сведения можно найти [в статье Защита системы Макинтош от вредоносных программ](https://support.apple.com/kb/PH25087).

**Включение защиты с брандмауэром**<p>
Используйте параметры брандмауэра для защиты компьютера Макинтош от нежелательного контакта, инициированного другими компьютерами при наличии подключения к Интернету или сети. Без этой защиты ваш Mac-адрес может быть более уязвим для несанкционированного доступа. Для получения инструкций обратитесь к разделу [о брандмауэре приложения](https://support.apple.com/HT201642) .
