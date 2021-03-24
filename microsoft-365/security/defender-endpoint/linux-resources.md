---
title: AtP Защитника Майкрософт для ресурсов Linux
ms.reviewer: ''
description: Описывает ресурсы atP Microsoft Defender для Linux, в том числе, как удалить его, как собирать диагностические журналы, команды CLI и известные проблемы с продуктом.
keywords: Microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 08dd8a3ff5f0b55d7fec8decd41f1120ca05077a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073765"
---
# <a name="resources"></a>Ресурсы

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Сбор диагностических сведений

Если вы можете воспроизвести проблему, сначала повысить уровень ведения журнала, запустить систему в течение некоторого времени, а затем восстановить уровень ведения журнала по умолчанию.

1. Повышение уровня ведения журнала:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Воспроизвести проблему.

3. Запустите следующую команду, чтобы выполнить back up Defender для журналов Endpoint. Файлы будут храниться внутри архива .zip.

   ```bash
   sudo mdatp diagnostic create
   ```

    Эта команда также распечатает путь файла к резервному копированию после успешной операции:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Восстановление уровня ведения журнала:

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Проблемы с установкой журнала

Если ошибка возникает во время установки, установщик будет сообщать только об общем сбое.

Подробный журнал будет сохранен до `/var/log/microsoft/mdatp_install.log` . Если во время установки вы испытываете проблемы, отправьте нам этот файл, чтобы мы могли помочь диагностировать причину.

## <a name="uninstall"></a>Uninstall

Существует несколько способов удалить Defender для конечной точки для Linux. Если вы используете средство конфигурации, например Puppet, выполните инструкции по деинсталлации пакета для средства конфигурации.

### <a name="manual-uninstallation"></a>Ручная отмывка

- `sudo yum remove mdatp` для RHEL и вариантов (CentOS и Oracle Linux).
- `sudo zypper remove mdatp` для SLES и вариантов.
- `sudo apt-get purge mdatp` для систем Ubuntu и Debian.

## <a name="configure-from-the-command-line"></a>Настройка из командной строки

Из командной строки можно выполнять важные задачи, такие как управление настройками продуктов и запуск сканирования по запросу.

### <a name="global-options"></a>Глобальные параметры

По умолчанию средство командной строки выводит результат в формате, читаемом для человека. Кроме того, средство также поддерживает вывод результатов в качестве JSON, что полезно для сценариев автоматизации. Чтобы изменить вывод на JSON, `--output json` передай любую из ниженаводных команд.

### <a name="supported-commands"></a>Поддерживаемые команды

В следующей таблице перечислены команды для некоторых наиболее распространенных сценариев. Запустите `mdatp help` из терминала, чтобы просмотреть полный список поддерживаемых команд.

|Группа                 |Сценарий                                                |Команда                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Конфигурация         |Включите/отключите защиту в режиме реального времени                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Конфигурация         |Включите/отключите облачную защиту                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Конфигурация         |Включите/отключите диагностику продукта                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Конфигурация         |Включите/отключите автоматическую отправку образца                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Конфигурация         |Включите и отключите пассивный режим AV                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Конфигурация         |Добавление или удаление исключения антивируса для расширения файла  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Конфигурация         |Добавление или удаление исключения антивируса для файла            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Конфигурация         |Добавление или удаление исключения антивируса для каталога       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Конфигурация         |Добавление или удаление исключения антивируса для процесса         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Конфигурация         |Список всех исключений антивируса                           |`mdatp exclusion list`                                                 |
|Конфигурация         |Добавление имени угрозы в разрешенный список                   |`mdatp threat allowed add --name [threat-name]`                        |
|Конфигурация         |Удаление имени угрозы из разрешенного списка              |`mdatp threat allowed remove --name [threat-name]`                     |
|Конфигурация         |Список всех разрешенных имен угроз                           |`mdatp threat allowed list`                                            |
|Конфигурация         |Включив защиту PUA                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Конфигурация         |Отключение защиты PUA                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Конфигурация         |Включим режим аудита для защиты PUA                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnostics           |Изменение уровня журнала                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnostics           |Создание журналов диагностики                                |`mdatp diagnostic create --path [directory]`                           |
|Здравоохранение                |Проверка состояния продукта                              |`mdatp health`                                                         |
|Защита            |Сканирование пути                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Защита            |Быстрое сканирование                                         |`mdatp scan quick`                                                     |
|Защита            |Полное сканирование                                          |`mdatp scan full`                                                      |
|Защита            |Отмена текущего сканирования по запросу                        |`mdatp scan cancel`                                                    |
|Защита            |Запрос обновления сведений о безопасности                  |`mdatp definitions update`                                             |
|История защиты    |Распечатать всю историю защиты                       |`mdatp threat list`                                                    |
|История защиты    |Сведения об угрозах                                      |`mdatp threat get --id [threat-id]`                                    |
|Управление карантином |Список всех карантинов                              |`mdatp threat quarantine list`                                         |
|Управление карантином |Удаление всех файлов из карантина                    |`mdatp threat quarantine remove-all`                                   |
|Управление карантином |Добавление файла, обнаруженного в качестве угрозы карантину       |`mdatp threat quarantine add --id [threat-id]`                         |
|Управление карантином |Удаление файла, обнаруженного в качестве угрозы из карантина  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Управление карантином |Восстановление файла из карантина                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Обнаружение и реагирование конечных точек |Настройка раннего предварительного просмотра (неиспользована)                    |`mdatp edr early-preview [enable|disable]`                             |
|Обнаружение и реагирование конечных точек |Set group-id                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Обнаружение и реагирование конечных точек |Тег Set/Remove, только `GROUP` поддерживаемый        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Обнаружение и реагирование конечных точек |исключения из списка (корневой)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Сведения портала Microsoft Defender для конечных точек

На портале Defender for Endpoint вы увидите две категории сведений:

- Антивирусные оповещений, в том числе:
  - Severity
  - Тип сканирования
  - Сведения об устройстве (имя хозяина, идентификатор устройства, идентификатор клиента, версия приложения и тип ОС)
  - Сведения о файле (имя, путь, размер и хаш)
  - Сведения об угрозах (имя, тип и состояние)
- Сведения об устройстве, в том числе:
  - Идентификатор устройства
  - Идентификатор клиента
  - Версия приложения.
  - Hostname (Имя узла)
  - Тип ОС
  - Версия ОС
  - Компьютерная модель
  - Архитектура процессора
  - Является ли устройство виртуальной машиной

### <a name="known-issues"></a>Известные проблемы

- На странице компьютерной информации портала Центра безопасности Microsoft Defender можно увидеть "Отсутствие данных датчиков, нарушение связи", даже если продукт работает как ожидалось. Мы работаем над решением этой проблемы.
- Во время входа в систему пользователи не отображаются на портале Центра безопасности Защитника Майкрософт.
- В рассылках SUSE, если установка *libatomic1* не удается, необходимо проверить, зарегистрирована ли ваша ОС:

   ```bash
   sudo SUSEConnect --status-text
   ```
