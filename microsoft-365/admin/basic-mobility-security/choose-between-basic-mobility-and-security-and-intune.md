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
description: Базовые функции мобильности и безопасности являются частью планов Microsoft 365.
ms.openlocfilehash: cfd1a68c313d1a1335490e2b8d6938de192fe3f3
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877096"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Выбор между базовой мобильностью и безопасностью или Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) — это автономный продукт, включенный в некоторые планы Microsoft 365, в то время как Basic Mobility and Security входит в состав планов Microsoft 365. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Доступность базовой мобильности и безопасности и Intune
 
Базовые мобильность и безопасность и Intune включены в различные планы, описанные в следующей таблице.

| План | Basic Mobility + Security | Microsoft Intune |
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
|Microsoft 365 для образования A1 |Да|Да|
|Microsoft 365 для образования A3 |Да|Да|
|Microsoft 365 для образования A5 |Да|ДА|
|Microsoft Intune |Нет|Да|
|Enterprise Mobility & Security E3 |Нет|Да|
|Enterprise Mobility & Security E5 |Нет|Да|

>[!NOTE]
>Если вы уже используете Microsoft Intune, вы не можете начать использовать Basic Mobility and Security.

 Подробные сведения см. в описании служб [платформы Microsoft 365 и Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Различия в возможностях

Microsoft Intune и встроенные функции Basic Mobility и Security дают возможность управлять мобильными устройствами в организации, но существуют ключевые различия в возможностях, описанные в следующей таблице.

>[!NOTE]
>Вы можете управлять пользователями и их мобильными устройствами с помощью Intune и Basic Mobility and Security в одной организации Microsoft 365 бизнес стандартный, сначала настроив Basic Mobility and Security, а затем добавив *Microsoft Intune.* Это позволяет выбрать базовые функции мобильности и безопасности или более функции решения Intune. Назначьте лицензию Intune, чтобы включить функции Intune.

| Функциональная область | Выделения функций | Basic Mobility + Security | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Типы устройств|Управление различными платформами ОС и основными вариантами режима управления. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Соответствие устройства требованиям|Установите и управляйте политиками безопасности, например блокировкой ПИН-кодов на уровне устройства и обнаружением разбейки. |Ограничения на устройствах с Android 9 и более поздних версий. См. [сведения.](capabilities.md) |Да|
|Условный доступ на основе соответствия устройств требованиям |Запретить несоотвершенным устройствам доступ к корпоративной электронной почте и данным из облака. |Не поддерживается в Windows 10.<br/>Ограничивается управлением доступом к Exchange Online, SharePoint Online и Outlook. |Да |
|Конфигурация устройства  |Настройка параметров устройства (например, отключение камеры)|Ограниченный набор параметров.|Да|
|Соответствие устройства требованиям  |Установите и управляйте политиками безопасности, например блокировкой ПИН-кодов на уровне устройства и обнаружением разбейки. |Ограничения на устройствах с Android 9 и более поздних версий. См. [сведения.](capabilities.md) |Да|
|Профили электронной почты  |Подготовка на устройстве своего профиля электронной почты. |Да|Да|
|Профили Wi-Fi |Подготовка на устройстве своего профиля Wi-Fi. |Нет|Да|
|Профили VPN |Подготовка на устройстве своего VPN-профиля. |Нет|Да|
|Базовое управление приложениями Mobility and Security  |Развертывание внутренних бизнес-приложений и из магазинов приложений для пользователей. |Нет|Да|
|Защита мобильных приложений  |Включите для пользователей безопасный доступ к корпоративной информации с помощью мобильных и бизнес-приложений Office, которые они знают, обеспечивая безопасность данных, помогая ограничить такие действия, как копирование, вырезание, ветвь и сохранение, только тем приложениям, которым удалось управлять для корпоративных данных. Работает, даже если устройства не зарегистрированы в Basic Mobility and Security. См. "Защита данных приложения с помощью политик MAM". |Нет|Да|
|Управляемый браузер  |Включить более безопасный просмотр веб-страниц с помощью приложения Edge. |Нет|Да|
|Программы автоматической регистрации Autopilot) |Регистрация большого количества корпоративных устройств, упрощая настройку пользователей. |Нет|Да|
|||

Помимо функций, перечисленных в предыдущей таблице, basic Mobility and Security и Intune включают набор удаленных действий, которые отправляют команды на устройства через Интернет. Например, вы можете удалить данные Office с устройства сотрудника, оставив персональные данные на месте (удалить), удалить приложения Office с устройства сотрудника (стирать) или сбросить заводские параметры устройства (полная стирка). 

Основные удаленные действия по мобильности и безопасности включают в себя отставку, стираемость и полную стираемость. Дополнительные сведения о действиях с базовой мобильностью и безопасностью см. в сведениях о возможностях [Basic Mobility and Security.](capabilities.md)

В Intune имеется следующий набор действий:

-   Сброс Autopilot (только для Windows)
-  [Поворот клавиш BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (только для Windows)
-  [Использование стирки, стирать или вручную открепить устройство](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Отключение местонахождения активации](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (только для iOS)
-  [Новое начало](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (только для Windows)
- [Полная проверка](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Только в Windows 10)
- [Поиск устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (только для iOS)
- [Режим потери](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (только для iOS) — [быстрая проверка](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(только для Windows 10)
- [Удаленное управление для Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Удаленная блокировка](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Переименование устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Сброс перезапуска](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [пароля](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (только для Windows)
-  Обновление Защитник Windows безопасности (только для Windows)
-  Сброс ПИН-кода в Windows 10 (только для Windows)
-  [Отправка пользовательских уведомлений](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Синхронизация устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Дополнительные сведения о действиях Intune см. в документации [по Microsoft Intune.](https://docs.microsoft.com/mem/intune/)
