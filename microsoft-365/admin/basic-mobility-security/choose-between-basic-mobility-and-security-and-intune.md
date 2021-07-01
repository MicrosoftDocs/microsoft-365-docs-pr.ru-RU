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
description: Базовая мобильность и безопасность являются частью Microsoft 365 планов.
ms.openlocfilehash: 869968fa46e09fbc7a983957a83a9ad308c9f40c
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228271"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Выбор между базовой мобильностью и безопасностью или Intune

[Microsoft Intune](/mem/intune/) является автономным продуктом, включенным с определенными Microsoft 365 планами, в то время как Basic Mobility and Security является частью Microsoft 365 планов.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Доступность базовой мобильности и безопасности и intune

Основные функции мобильности и безопасности и Intune включены в различные планы, описанные в следующей таблице.

| Планирование | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|
|Приложения Microsoft 365|Да|Нет|
|Microsoft 365 бизнес базовый|Да|Нет|
|Microsoft 365 бизнес стандарт|Да|Нет|
|Office 365 E1 |Да|Нет|
|Office 365 E3 |Да|Нет|
|Office 365 E5 |Да|Нет|
|Microsoft 365 бизнес премиум |Да|Да|
|Microsoft 365 Firstline 3 |Да|Да|
|Microsoft 365 корпоративный E3 |Да|Да|
|Microsoft 365 корпоративный E5 |Да|Да|
|Microsoft 365 для образования A1 |Да|Да|
|Microsoft 365 для образования A3 |Да|Да|
|Microsoft 365 для образования A5 |Да|ДА|
|Microsoft Intune |Нет|Да|
|Enterprise Мобильность & безопасности E3 |Нет|Да|
|Enterprise Mobility и Security E5 |Нет|Да|

> [!NOTE]
> Вы не можете начать использовать Basic Mobility и Security, если вы уже используете Microsoft Intune.

 Подробные сведения [см. в Microsoft 365 и Office 365 описания служб платформы.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)

## <a name="differences-in-capabilities"></a>Различия в возможностях

Microsoft Intune и встроенная базовая мобильность и безопасность дают возможность управлять мобильными устройствами в организации, но существуют ключевые различия в возможностях, описанных в следующей таблице.

> [!NOTE]
> Вы можете управлять пользователями и их мобильными устройствами с помощью Intune и Basic Mobility and Security в одной Microsoft 365 бизнес стандарт организации, сначала настроив basic *Mobility and Security,* а затем добавив Microsoft Intune . Это позволяет выбрать базовую мобильность и безопасность или более богатое функцией решение Intune. Назначьте лицензию Intune, чтобы включить функции Intune.

| Функциональная область | Основные моменты функций | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Типы устройств|Управление различными платформами ОС и основными вариантами режима управления. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>MAC OS, iPad OS|
|Соответствие устройства требованиям|Установите и управляйте политиками безопасности, например блокировкой ПИН-кода уровня устройства и обнаружением побега из тюрьмы. |Ограничения на устройствах с Android 9 и более поздними версиями. Сведения см. в [материале](capabilities.md). |Да|
|Условный доступ на основе соответствия требованиям устройств |Запретить незавершенным устройствам получать доступ к корпоративной электронной почте и данным из облака. |Не поддерживается Windows 10.<br/>Ограничивается управлением доступом Exchange Online, SharePoint и Outlook. |Да |
|Конфигурация устройства  |Настройка параметров устройства (например, отключение камеры)|Ограниченный набор параметров.|Да|
|Соответствие устройства требованиям  |Установите и управляйте политиками безопасности, например блокировкой ПИН-кода уровня устройства и обнаружением побега из тюрьмы. |Ограничения на устройствах с Android 9 и более поздними версиями. Сведения см. в [материале](capabilities.md). |Да|
|Профили электронной почты  |Предоставление родного профиля электронной почты на устройстве. |Да|Да|
|Профили WiFi |Предоставление родного профиля WiFi на устройстве. |Нет|Да|
|ПРОФИЛИ VPN |Предоставление на устройстве родного VPN-профиля. |Нет|Да|
|Управление мобильными приложениями  |Развертывание внутренних бизнес-приложений и магазинов приложений для пользователей. |Нет|Да|
|Защита мобильных приложений  |Позволяет пользователям безопасно получать доступ к корпоративной информации с помощью Office мобильных и бизнес-приложений, которые они знают, обеспечивая безопасность данных, помогая ограничить действия, такие как копирование, вырезать, вклеить и сохранить только те приложения, управляемые для корпоративных данных. Работает, даже если устройства не зарегистрированы в Basic Mobility and Security. См. в приложении Protect data using MAM policies. |Нет|Да|
|Управляемый браузер  |Включить более безопасный веб-просмотр с помощью приложения Edge. |Нет|Да|
|Zero touch enrollment programs (AutoPilot) |Регистрация большого числа корпоративных устройств, упрощая настройку пользователей. |Нет|Да|
|||

Помимо функций, перечисленных в предыдущей таблице, basic Mobility and Security и Intune включают набор удаленных действий, которые отправляют команды устройствам через Интернет. Например, можно удалить Office с устройства сотрудника, оставив личные данные на месте (удалить), удалить Office приложения с устройства сотрудника (wipe) или сбросить устройство в заводские параметры (полное удаление).

Удаленные действия Basic Mobility и Security включают в себя отставку, вытирать и полностью стирать. Дополнительные сведения о действиях базовой мобильности и безопасности см. в дополнительных сведениях [о возможностях базовой](capabilities.md)мобильности и безопасности.

В Intune у вас есть следующий набор действий:

-   Сброс автопилота (Windows только
-  [Поворот ключа Bitlocker](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Windows только)
-  [Использование стирки, стирки или вручную разгрузки устройства](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Отключение лока активации](/mem/intune/remote-actions/device-activation-lock-disable)   (только для iOS)
-  [Новое начало](/mem/intune/remote-actions/device-fresh-start)   (Windows только)
- [Полное сканирование](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Windows 10 только)
- [Найдите устройство](/mem/intune/remote-actions/device-locate)   (только для iOS)
- [Потерянный режим](/mem/intune/remote-actions/device-lost-mode)   (только для iOS) — [быстрое](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)сканирование (только Windows 10)
- [Удаленное управление для Android](/mem/intune/remote-actions/teamviewer-support)
- [Удаленная блокировка](/mem/intune/remote-actions/device-remote-lock)
- [Устройство переименования](/mem/intune/remote-actions/device-rename)
-  [Перезагрузка](/mem/intune/remote-actions/device-passcode-reset) [](/mem/intune/remote-actions/device-restart)пароля   (только Windows)
-  Обновление Защитник Windows безопасности (только Windows)
-  Windows 10 Сброс ПИН-кода (только Windows)
-  [Отправка пользовательских уведомлений](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad ОС)
-  [Синхронизация устройства](/mem/intune/remote-actions/device-sync)

Дополнительные сведения о действиях Intune см. в Microsoft Intune [документации.](/mem/intune/)