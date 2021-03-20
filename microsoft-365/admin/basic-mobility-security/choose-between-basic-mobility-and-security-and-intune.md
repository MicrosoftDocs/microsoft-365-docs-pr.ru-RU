---
title: Выбор между базовой мобильностью и безопасностью и Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Базовая мобильность и безопасность являются частью планов Microsoft 365.
ms.openlocfilehash: b7b1d229e87a313a9567daed87f03452b1925a65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904268"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Выбор между базовой мобильностью и безопасностью или Intune

[Microsoft Intune —](/mem/intune/) это автономный продукт, включенный с определенными планами Microsoft 365, в то время как Basic Mobility and Security входит в планы Microsoft 365.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Доступность базовой мобильности и безопасности и intune

Основные функции мобильности и безопасности и Intune включены в различные планы, описанные в следующей таблице.

| Планирование | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|
|Приложения Microsoft 365|Да|Нет|
|Microsoft 365 бизнес базовый|Да|Нет|
|Microsoft 365 бизнес стандарт|Да|Нет|
|Office 365 E1 |Да|Нет|
|Office 365 E3 |Да|Нет|
|Office 365 E5 |Да|Нет|
|Microsoft 365 бизнес премиум |Да|Да|
|Microsoft 365 Firstline 3 |Да|Да|
|Microsoft 365 корпоративный E3 |Да|Да|
|Microsoft 365 корпоративный E5 |Да|Да|
|Microsoft 365 Education A1 |Да|Да|
|Microsoft 365 для образования A3 |Да|Да|
|Microsoft 365 для образования A5 |Да|ДА|
|Microsoft Intune |Нет|Да|
|Корпоративная мобильность & безопасности E3 |Нет|Да|
|Корпоративная мобильность & безопасности E5 |Нет|Да|

>[!NOTE]
>Вы не можете начать использовать Basic Mobility and Security, если вы уже используете Microsoft Intune.

 Подробные сведения см. в описаниях служб [платформ Microsoft 365 и Office 365.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Различия в возможностях

Microsoft Intune и встроенная базовая мобильность и безопасность дают возможность управлять мобильными устройствами в организации, но существуют ключевые различия в возможностях, описанных в следующей таблице.

>[!NOTE]
>Вы можете управлять пользователями и их мобильными устройствами с помощью Intune и Basic Mobility and Security в той же организации Microsoft 365 Business Standard, сначала установив базовую мобильность и безопасность, а затем добавив *Microsoft Intune.* Это позволяет выбрать базовую мобильность и безопасность или более богатое функцией решение Intune. Назначьте лицензию Intune, чтобы включить функции Intune.

| Функциональная область | Основные моменты функций | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Типы устройств|Управление различными платформами ОС и основными вариантами режима управления. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>MAC OS, iPad OS|
|Соответствие устройства требованиям|Установите и управляйте политиками безопасности, например блокировкой ПИН-кода уровня устройства и обнаружением побега из тюрьмы. |Ограничения на устройствах с Android 9 и более поздними версиями. Сведения см. в [материале](capabilities.md). |Да|
|Условный доступ на основе соответствия требованиям устройств |Запретить незавершенным устройствам получать доступ к корпоративной электронной почте и данным из облака. |Не поддерживается в Windows 10.<br/>Ограничивается управлением доступом к Exchange Online, SharePoint Online и Outlook. |Да |
|Конфигурация устройства  |Настройка параметров устройства (например, отключение камеры)|Ограниченный набор параметров.|Да|
|Соответствие устройства требованиям  |Установите и управляйте политиками безопасности, например блокировкой ПИН-кода уровня устройства и обнаружением побега из тюрьмы. |Ограничения на устройствах с Android 9 и более поздними версиями. Сведения см. в [материале](capabilities.md). |Да|
|Профили электронной почты  |Предоставление родного профиля электронной почты на устройстве. |Да|Да|
|Профили WiFi |Предоставление родного профиля WiFi на устройстве. |Нет|Да|
|ПРОФИЛИ VPN |Предоставление на устройстве родного VPN-профиля. |Нет|Да|
|управление мобильными приложениями;  |Развертывание внутренних бизнес-приложений и магазинов приложений для пользователей. |Нет|Да|
|Защита мобильных приложений  |Включите пользователям возможность безопасного доступа к корпоративной информации с помощью мобильных и бизнес-приложений Office, которые они знают, обеспечивая безопасность данных, помогая ограничить действия, такие как копирование, вырезать, вклеить и сохранить только те приложения, управляемые для корпоративных данных. Работает, даже если устройства не зарегистрированы в Basic Mobility and Security. См. в приложении Protect data using MAM policies. |Нет|Да|
|Управляемый браузер  |Включить более безопасный веб-просмотр с помощью приложения Edge. |Нет|Да|
|Zero touch enrollment programs (AutoPilot) |Регистрация большого числа корпоративных устройств, упрощая настройку пользователей. |Нет|Да|
|||

Помимо функций, перечисленных в предыдущей таблице, basic Mobility and Security и Intune включают набор удаленных действий, которые отправляют команды устройствам через Интернет. Например, можно удалить данные Office с устройства сотрудника, оставив личные данные на месте (удалить), удалить приложения Office с устройства сотрудника (протрите) или сбросить устройство в заводские параметры (полное удаление). 

Удаленные действия Basic Mobility и Security включают в себя отставку, вытирать и полностью стирать. Дополнительные сведения о действиях базовой мобильности и безопасности см. в дополнительных сведениях [о возможностях базовой](capabilities.md)мобильности и безопасности.

В Intune у вас есть следующий набор действий:

-   Сброс автопилота (только для Windows)
-  [Поворот ключа Bitlocker](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Только для Windows)
-  [Использование стирки, стирки или вручную разгрузки устройства](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Отключение лока активации](/mem/intune/remote-actions/device-activation-lock-disable)   (только для iOS)
-  [Новое начало](/mem/intune/remote-actions/device-fresh-start)   (Только для Windows)
- [Полное сканирование](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Только для Windows 10)
- [Найдите устройство](/mem/intune/remote-actions/device-locate)   (только для iOS)
- [Потерянный режим](/mem/intune/remote-actions/device-lost-mode)   (только для iOS) — [быстрое сканирование](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(только для Windows 10)
- [Удаленное управление для Android](/mem/intune/remote-actions/teamviewer-support)
- [Удаленная блокировка](/mem/intune/remote-actions/device-remote-lock)
- [Устройство переименования](/mem/intune/remote-actions/device-rename)
-  [Перезагрузка перезапуска](/mem/intune/remote-actions/device-passcode-reset) [пароля](/mem/intune/remote-actions/device-restart)   (только для Windows)
-  Обновление Защитник Windows безопасности (только для Windows)
-  Сброс ПИН-кода Windows 10 (только для Windows)
-  [Отправка пользовательских уведомлений](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Синхронизация устройства](/mem/intune/remote-actions/device-sync)

Дополнительные сведения о действиях Intune см. в [документации Microsoft Intune.](/mem/intune/)