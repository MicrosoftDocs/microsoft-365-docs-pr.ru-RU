---
title: Настройка антивирусная программа в Microsoft Defender групповой политики
description: Узнайте, как использовать групповую политику для настройки и управления антивирусная программа в Microsoft Defender конечных точек в Microsoft Defender для конечной точки.
keywords: групповой политики, GPO, конфигурации, параметры
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/07/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 81cba445482b1fceb8bd520f2be88d55db2a47fb
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296735"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Используйте параметры групповой политики для настройки и управления антивирусная программа в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

[Групповая политика может](/windows/win32/srvnodes/group-policy) настраивать и управлять антивирусная программа в Microsoft Defender конечными точками.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>Настройка антивирусная программа в Microsoft Defender с помощью групповой политики

В общем, вы можете использовать следующую процедуру для настройки или изменения параметров антивирусная программа в Microsoft Defender групповой политики:

1. На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики (GPO), который необходимо настроить, и нажмите **кнопку Изменить**.

2. С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера.**

3. Щелкните **административные шаблоны**.

4. Расширь **дерево, Windows компоненты**  >  **антивирусная программа в Microsoft Defender**.

5. Расширь раздел (который  называется Расположение в таблице в этом разделе), содержащий параметр, который необходимо настроить, дважды щелкните параметр, чтобы открыть его, и внести изменения в конфигурацию.

6. [Развертывание обновленного GPO, как обычно.](/windows/win32/srvnodes/group-policy) 

## <a name="group-policy-settings-and-resources"></a>Параметры и ресурсы групповой политики

В следующей таблице в этом разделе перечислены параметры групповой политики, доступные в Windows 10 версии 1703, а также ссылки на соответствующую тему в этой библиотеке документации (где это применимо). 

> [!TIP]
> Скачайте таблицу Параметры групповой политики для обновления Windows 10 мая [2020 г. (2004 г.).](https://www.microsoft.com/download/101451) В этой электронной таблице перечислены параметры политики для компьютеров и конфигураций пользователей, включенных в файлы административных шаблонов, доставленные с обновлением за Windows 10 мая 2020 г. (2004 г.). Эти параметры политики можно настроить при редактировании объектов групповой политики.

| Location | Параметр | Статья |
|:---|:---|:---|
| Клиентский интерфейс | Включить безголовый режим пользовательского интерфейса | [Запретить пользователям видеть или взаимодействовать с антивирусная программа в Microsoft Defender пользовательским интерфейсом](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Клиентский интерфейс | Отображение дополнительных текстов для клиентов при необходимости выполнения действия | [Настройка уведомлений, которые отображаются в конечных точках](configure-notifications-microsoft-defender-antivirus.md) |
| Клиентский интерфейс | Подавление всех уведомлений | [Настройка уведомлений, которые отображаются в конечных точках](configure-notifications-microsoft-defender-antivirus.md) |
| Клиентский интерфейс | Подавляет уведомления о перезагрузке | [Настройка уведомлений, которые отображаются в конечных точках](configure-notifications-microsoft-defender-antivirus.md) |
| Исключения | Исключения расширения | [Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования](configure-exclusions-microsoft-defender-antivirus.md) |
| Исключения | Исключения пути | [Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования](configure-exclusions-microsoft-defender-antivirus.md) |
| Исключения | Исключения процессов | [Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования](configure-exclusions-microsoft-defender-antivirus.md) | 
| Исключения | Отключение автоматических исключений | [Настройка и проверка исключений в антивирусная программа в Microsoft Defender сканирования](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPS | Настройка функции "Блок с первого взгляда" | [Включить блок с первого взгляда](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPS | Присоединяйтесь к Microsoft MAPS | [Включение облачной защиты](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Отправка образцов файлов при необходимости дополнительного анализа | [Включение облачной защиты](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Настройка переопределения локального параметра для отчетов в Microsoft MAPS | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Настройка расширенной облачной проверки | [Настройка времени ожидания блокировки облака](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Выберите уровень облачной защиты | [Указать уровень облачной защиты](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Система сетевого контроля | Укажите дополнительные наборы определений для проверки сетевого трафика | [Укажите дополнительные наборы определений для проверки сетевого трафика](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| Система сетевого контроля | Включив выход на пенсию определения | [Настройка выхода на пенсию определения](turn-on-definition-retirement.md)  |
| Система сетевого контроля | Включив распознавание протокола | [Включив распознавание протокола](turn-on-protocol-recognition.md)  |
| Карантин | Настройка переопределения локального параметра для удаления элементов из папки Карантина | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Карантин | Настройка удаления элементов из папки Карантина | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Настройка переопределения локального параметра для мониторинга действий файла и программы на компьютере | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Настройка переопределения локального параметра для мониторинга действий входящих и исходяющих файлов | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Настройка переопределения локального параметра для сканирования всех загруженных файлов и вложений | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Настройка переопределения локального параметра для включения мониторинга поведения | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Настройка переопределения локального параметра, чтобы включить защиту в режиме реального времени | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Определение максимального размера скачаемых файлов и вложений, которые необходимо отсканировать | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Мониторинг активности файлов и программ на компьютере | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Сканирование всех загруженных файлов и вложений | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Отключение защиты в режиме реального времени | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Включив мониторинг поведения | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Включаем сканирование процессов при включенной защите в режиме реального времени | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Включив необработанные уведомления о записи тома | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Защита в режиме реального времени | Настройка мониторинга для входящих и исходяющих действий файлов и программ | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Исправление | Настройка переопределения локального параметра на время суток для выполнения запланированного полного сканирования для завершения восстановления | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Исправление | Укажите день недели для выполнения запланированного полного сканирования для завершения восстановления | [Настройка запланированных антивирусная программа в Microsoft Defender сканирования](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Исправление | Укажите время суток для выполнения запланированного полного сканирования, чтобы завершить исправление | [Настройка запланированных антивирусная программа в Microsoft Defender сканирования](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Reporting | Отключение расширенных уведомлений | [Настройка уведомлений, которые отображаются в конечных точках](configure-notifications-microsoft-defender-antivirus.md)
| Root | Отключите антивирусная программа в Microsoft Defender | Не используется (Этот параметр  должен быть настроен не для обеспечения правильной работы любых установленных сторонних антивирусных приложений)
| Root | Определение адресов для обхода прокси-сервера | Не используется |
| Root | Определение прокси-автоконфига (.pac) для подключения к сети | Не используется |
| Root | Определение прокси-сервера для подключения к сети | Не используется |
| Root | Настройка поведения локального администратора для объединения списков | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Root | Разрешить запуск службы антивирусных программ с обычным приоритетом | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Разрешить всегда работать службе антивирусных программ | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Отключение плановых исправлений | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Рандомизация запланированного времени задач | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Проверка | Разрешить пользователям приостанавлить сканирование | Запретить пользователям видеть или взаимодействовать с [пользовательским интерфейсом](prevent-end-user-interaction-microsoft-defender-antivirus.md) антивирусная программа в Microsoft Defender (не поддерживается Windows 10) |
| Проверка | Проверьте последние определения вирусов и программ-шпионов перед запуском запланированного сканирования | [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Проверка | Определение количества дней, после которых принудительное сканирование догонять | [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Проверка | Включите полное сканирование | [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Проверка | Включите быстрое сканирование | [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Проверка | Настройка переопределения локального параметра для максимального процента использования ЦП | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Проверка | Настройка переопределения локального параметра для дня проверки расписания | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Проверка | Настройка переопределения локального параметра для запланированного быстрого сканирования | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Проверка | Настройка переопределения локального параметра для запланированного времени сканирования | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Проверка | Настройка переопределения локального параметра для типа сканирования для запланированного сканирования | [Предотвращение или разрешение пользователям локально изменять параметры политики](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Проверка | Создание точки восстановления системы | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Проверка | Включаем удаление элементов из папки истории сканирования | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Проверка | Включаем юристию | [Включить и настроить антивирусная программа в Microsoft Defender защиту и мониторинг](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Проверка | Включив сканирование электронной почты | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Включив сканирование точек репаринга | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Запуск полного сканирования на картах сетевых дисков | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Сканирование архивных файлов | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Сканирование сетевых файлов | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Сканирование упакованных исполняемых исполняемых | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Сканирование съемных дисков | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Укажите максимальную глубину для сканирования архивных файлов | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Укажите максимальный процент использования ЦП во время проверки | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Укажите максимальный размер отсканированных архивных файлов | [Настройка параметров сканирования в антивирусная программа в Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Проверка | Укажите день недели для запуска запланированного сканирования | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Проверка | Укажите интервал для быстрого сканирования в день | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Проверка | Укажите тип сканирования, который необходимо использовать для запланированного сканирования | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Проверка | Укажите время ежедневного быстрого сканирования | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Проверка | Укажите время суток для запуска запланированного сканирования | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Проверка | Запуск запланированного сканирования только в том случае, если компьютер находится на компьютере, но не используется | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Разрешить обновления сведений о безопасности из Обновления Майкрософт | [Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Разрешить обновления сведении о безопасности при работе с питанием от батареи | [Управление обновлениями для мобильных устройств и виртуальных машин (ВМ)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Разрешить уведомления для отключения отчетов на основе определений в Microsoft MAPS | [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Разрешить обновления сведений о безопасности в режиме реального времени на основе отчетов в Microsoft MAPS | [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Проверка последних определений вирусов и программ-шпионов при запуске | [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Определение файловой доли для скачивания обновлений разведки безопасности | [Управление обновлениями антивирусная программа в Microsoft Defender защиты и безопасности](manage-protection-updates-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Определите количество дней, после которых требуется обновление сведений о безопасности | [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Определение количества дней до того, как определения программ-шпионов считаются устарели | [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Определение количества дней до того, как определения вирусов считаются устарели | [Управление обновлениями для устарели конечных точек](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Определение порядка источников для скачивания обновлений разведки безопасности | [Управление обновлениями антивирусная программа в Microsoft Defender защиты и безопасности](manage-protection-updates-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Инициировать обновление сведении о безопасности при запуске | [Управление принудительными обновлениями на основе событий](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Укажите день недели для проверки обновлений разведки безопасности | [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Укажите интервал для проверки обновлений разведки безопасности | [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Укажите время проверки обновлений разведки безопасности | [Управление загрузкой и приложением обновлений защиты](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Обновления аналитики безопасности | Включив сканирование после обновления сведении безопасности | [Настройка запланированных сканов для антивирусная программа в Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Threats | Укажите уровни оповещений об угрозах, на которых по умолчанию не следует принимать меры при обнаружении | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |
| Threats | Укажите угрозы, при которых по умолчанию не следует принимать меры при обнаружении | [Настройка исправлений для антивирусная программа в Microsoft Defender проверки](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>См. также

- [Справочные темы для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
