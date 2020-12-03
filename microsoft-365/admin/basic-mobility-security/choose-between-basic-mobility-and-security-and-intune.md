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
description: Базовые мобильность и безопасность входят в планы Microsoft 365.
ms.openlocfilehash: 8724b3dccbdb5949190ceda4b804b9f1f2a5d4b2
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561499"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Выбор между базовыми мобильностью и безопасностью или Intune

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) — это автономный продукт, включенный в определенные планы Microsoft 365, в то время как базовые мобильность и безопасность являются частью планов Microsoft 365. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Доступность базовых служб мобильной связи и безопасности и Intune
 
Как базовые мобильность, так и безопасность и Intune включены в различные планы, описанные в следующей таблице.

| Планирование | Базовые мобильность и безопасность | Microsoft Intune |
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
|Microsoft 365 для образования a1 |Да|Да|
|Microsoft 365 для образования A3 |Да|Да|
|Microsoft 365 для образования A5 |Да|ДА|
|Microsoft Intune |Нет|Да|
|Корпоративная мобильность & Security E3 |Нет|Да|
|Корпоративная мобильная & безопасность |Нет|Да|

>[!NOTE]
>Вы не можете приступать к использованию базовых функций мобильной связи и безопасности, если вы уже используете Microsoft Intune.

 Дополнительные сведения см. в [статье Microsoft 365 и описание службы платформы Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Различия в возможностях

Microsoft Intune и Встроенная базовая поддержка мобильности и безопасности предоставляют возможность управлять мобильными устройствами в Организации, но в приведенной ниже таблице есть основные различия в возможности.

>[!NOTE]
>Вы можете управлять пользователями и их мобильными устройствами, используя Intune и Basic Mobility и Security в одной организации Microsoft 365 бизнес Standard, *настраивая базовую мобильность и безопасность, а затем добавляя Microsoft Intune*. Это позволяет выбрать базовые мобильность и безопасность, а также более широкие возможности решения Intune. Назначьте лицензию Intune, чтобы включить функции Intune.

| Функциональная область | Основные функции | Базовые мобильность и безопасность | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Типы устройств|Управление различными платформами ОС и основными вариантами режима управления. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, iPad OS|
|Соответствие устройства требованиям|Задание и управление политиками безопасности, такими как блокировка ПИН-кода на уровне устройства и обнаружение жаилбреак. |Ограничения на устройствах с Android 9 и более поздних версий. [Подробнее](capabilities.md). |Да|
|Условный доступ на основе соответствия требованиям устройств |Предотвращение доступа несоответствующих требованиям устройств к корпоративным электронным письмам и данным из облака. |Не поддерживается в Windows 10.<br/>Ограниченный контроль доступа к Exchange Online, SharePoint Online и Outlook. |Да |
|Конфигурация устройства  |Настройка параметров устройств (например, отключение камеры)|Соответствие устройства требованиям|Задание и управление политиками безопасности, такими как блокировка ПИН-кода на уровне устройства и обнаружение жаилбреак. |Ограничения на устройствах с Android 9 и более поздних версий. [Подробнее](capabilities.md). |Да|
 |Ограниченный набор параметров. |Да|
|Профили электронной почты  |Подготовка собственного профиля электронной почты на устройстве. |Да|Да|
|Профили Wi-Fi |Подготовка собственного профиля Wi-Fi на устройстве. |Нет|Да|
|Профили VPN |Подготовка собственного профиля VPN на устройстве. |Нет|Да|
|Управление приложениями MDM |Развертывайте внутренние бизнес-приложения и из магазинов приложений для пользователей. |Нет|Да|
|MAM |Убедитесь, что ваши пользователи могут безопасно получать доступ к корпоративной информации с помощью приложений Office Mobile и бизнес-приложений, помогая ограничить действия, такие как копирование, вырезать, вставить и сохранить как, только для тех приложений, которые утверждены для корпоративных данных. |Нет|Да|
|Managed Browser  |Включение более безопасного веб-обзора с помощью пограничного приложения. |Нет|Да|
|Автопилот для программ регистрации с нулевым управлением. |Зарегистрировать большое количество корпоративных устройств, а затем упростить настройку пользователей. |Нет|Да|
|||

В дополнение к функциям, перечисленным в предыдущей таблице, базовые мобильность и безопасность и Intune включают набор удаленных действий, которые отправляют команды на устройства через Интернет. Например, вы можете удалить данные Office с устройства сотрудника, оставив личные данные на месте (не выполняя), удалять приложения Office с устройства (стирания) сотрудника или сбрасывать их в заводские настройки (полная очистка). 

Основные удаленные действия для мобильности и безопасности включают снятие с учета, очистку и полную очистку. Более подробную информацию об основных действиях по обеспечению мобильности и безопасности можно узнать в статье [возможности базового обеспечения безопасности и обеспечения безопасности](capabilities.md).

С помощью Intune можно получить следующий набор действий:

-   Автопилотный сброс (только для Windows)
-  [Ротация](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   ключей BitLocker (Только для Windows)
-  [Отмена регистрации устройства с помощью очистки, снятия с учета или вручную](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Отключить активацию Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (только для iOS)
-  [Начало обновления](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Только для Windows)
- [Полная проверка](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Только для Windows 10)
- [Обнаружение устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (только для iOS)
- Режим "потеряно" [Lost mode](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (только для iOS) — [Быстрая проверка](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(только для Windows 10)
- [Удаленное управление для Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Удаленная блокировка](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Переименование устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Сброс секретного кода](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) при [перезапуске](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (только для Windows)
-  Обновление службы анализа безопасности защитника Windows (только для Windows)
-  Сброс ПИН-кода Windows 10 (только для Windows)
-  [Отправка настраиваемых уведомлений](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Синхронизация устройства](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Для получения дополнительных сведений о действиях Intune обратитесь [к документации по Microsoft Intune](https://docs.microsoft.com/mem/intune/).
