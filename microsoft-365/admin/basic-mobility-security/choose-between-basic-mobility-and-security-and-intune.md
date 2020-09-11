---
title: Выбор между базовыми мобильностью и безопасностью и Intune
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
description: Базовые мобильность и безопасность являются частью планов Microsoft 365.
ms.openlocfilehash: df52d500c945275b62170ab16260f0c019340f73
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429930"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Выбор между базовыми мобильностью и безопасностью и Intune

Microsoft Intune это автономный продукт, включенный в определенные планы Microsoft 365, в то время как базовые & безопасности для мобильных устройств являются частью планов Microsoft 365. Оба варианта включены в различные планы, описанные в следующей таблице.

|**План**|**Базовые мобильность и безопасность**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Приложения Microsoft 365|Да|Нет|
|Microsoft 365 бизнес базовый|Да|Нет|
|Microsoft 365 бизнес стандарт|Да|Нет|
|Office 365 E1 |Да|Нет|
|Office 365 E3 |Да|Нет|
|Office 365 E5 |Да|Нет|
|Microsoft 365 бизнес премиум |Да|Да|
|Microsoft 365 задействование 3 |Да|Да|
|Microsoft 365 корпоративный E3 |Да|Да|
|Microsoft 365 корпоративный E5 |Да|Да|
|Microsoft 365 Едуктатион a1 |Да|Да|
|Microsoft 365 для образования A3 |Да|Да|
|Microsoft 365 для образования A5 |Да|ДА|
|Microsoft Intune |Нет|Да|
|Корпоративная мобильность & Security E3 |Нет|Да|
|Корпоративная мобильная & безопасность |Нет|Да|

>[!NOTE]
>Вы не можете приступать к использованию базовых функций мобильной связи и безопасности, если вы уже используете Microsoft Intune.

## <a name="differences-in-capabilities"></a>Различия в возможностях

Microsoft Intune и Встроенная базовая поддержка мобильности и безопасности предоставляют возможность управлять мобильными устройствами в Организации, но в приведенной ниже таблице есть основные различия в возможности.

>[!NOTE]
>Вы можете управлять пользователями и их мобильными устройствами, используя Intune и Basic Mobility и Security в одной организации Microsoft 365 бизнес Standard, настраивая базовую мобильность и безопасность, а затем добавляя Microsoft Intune. Это позволяет выбрать, следует ли управлять устройствами пользователя с помощью базовых возможностей мобильности и безопасности, а также с широкими возможностями решения Intune. В этом режиме Назначение лицензии определяет, с какой службой регистрируется устройство. Назначьте лицензию Intune, чтобы включить функции, которые доступны только для Intune.

|**Область функций**|**Основные функции**|**Базовые мобильность и безопасность**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Типы устройств|Различные платформы ОС и основные варианты режима управления. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS<br/>ОС iPad|
|Соответствие устройства требованиям|Задание и управление политиками безопасности, такими как блокировка ПИН-кода на уровне устройства и обнаружение жаилбреак. |Ограничения на устройствах с Android 9 и более поздних версий. Сведения о том, как [Основные возможности мобильной работы и обеспечения безопасности](capabilities.md).|Да|
|Условный доступ на основе соответствия требованиям устройств |Предотвращение доступа несоответствующих требованиям устройств к корпоративным электронным письмам и данным из облака. |— Не поддерживается в Windows 10.<br/>— Ограничено управление доступом к Exchange Online, SharePoint Online и службам Outlook. |Нет|
|Конфигурация устройства  |Настройка параметров устройств (например, отключение камеры). |Ограниченный набор параметров.Сведения о том, как [Основные возможности мобильной работы и обеспечения безопасности](capabilities.md). |Да|
|удаленные действия.  |Отправка команд на устройства через Интернет. Например, можно удалить данные Office с устройства сотрудника, оставив персональные данные на месте (снять с учета). |Прекращение использования<br/>Очистка<br/>Удалить|-Автопилотный сброс (только для Windows)<br/>- [Ротация](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   ключей BitLocker (Только для Windows)<br/>- [Удален](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Отключить активацию Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (только для iOS)<br/>- [Начало обновления](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Только для Windows)<br/>- [Полная проверка](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Только для Windows 10)<br/>- [Обнаружение устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (только для iOS)<br/>- Режим "потеряно" [Lost mode](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (только для iOS)<br/>- [Быстрая проверка](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(только для Windows 10)<br/>- [Удаленное управление для Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Удаленная блокировка](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Переименование устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Сброс секретного кода](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Перезапуск](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Только для Windows)<br/>- [Снять](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>Обновление службы анализа безопасности защитника Windows (только для Windows)<br/>-Установка ПИН-кода Windows 10 (только для Windows)<br/>- [Очистка](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Отправка настраиваемых уведомлений](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)<br/>- [Синхронизация устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|Профили электронной почты  |Подготовка собственного профиля электронной почты на устройстве. |Да|Да|
|Профили Wi-Fi |Подготовка собственного профиля Wi-Fi на устройстве. |Нет|Да|
|Профили VPN |Подготовка собственного профиля VPN на устройстве. |Нет|Да|
|Управление приложениями MDM  |Развертывайте внутренние бизнес-приложения и из магазинов приложений для пользователей. |Нет|Да|
|Защита мобильных приложений  |Разрешите пользователям безопасно получать доступ к корпоративным данным с помощью приложений Office Mobile и бизнес-компаний, которые им известны, а также обеспечивая защиту данных, позволяя ограничить действия, такие как копирование, вырезать, вставить и сохранить как, только для тех приложений, которые являются утвержденными для корпоративных данных. Работает даже в том случае, если устройства не зарегистрированы в MDM. В разделе Защита данных приложения с помощью политик MAM. |Нет|Да|
|Managed Browser  |Включение более безопасного веб-обзора с помощью пограничного приложения. |Нет|Да|
|Программы регистрации с нулевым числом сенсорных страниц |Зарегистрировать большое число корпоративных устройств, а затем упростить настройку пользователя. |Нет|Да|
