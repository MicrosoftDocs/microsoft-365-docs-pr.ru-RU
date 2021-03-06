---
title: Ресурсы для Microsoft Defender для конечной точки на Mac
description: Ресурсы для Microsoft Defender для конечной точки на Mac, в том числе как удалить его, как собирать диагностические журналы, команды CLI и известные проблемы с продуктом.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: fa5d5b4470644e1ff50af46a8dd3f035cd9b3184
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842870"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>Ресурсы для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Сбор диагностических сведений

Если вы можете воспроизвести проблему, увеличите уровень ведения журнала, запустите систему в течение некоторого времени и восстановите уровень ведения журнала по умолчанию.

1. Повышение уровня ведения журнала:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Воспроизведение проблемы

3. Запустите `sudo mdatp diagnostic create` для поддержки журналов Microsoft Defender для конечных точек. Файлы будут храниться в .zip архиве. Эта команда также распечатает путь файла к резервному копированию после успешной операции.

   > [!TIP]
   > По умолчанию журналы диагностики сохраняются до `/Library/Application Support/Microsoft/Defender/wdavdiag/` . Чтобы изменить каталог, в котором сохраняются диагностические журналы, перейдите в приведенную ниже команду, заменив `--path [directory]` `[directory]` нужный каталог.

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Восстановление уровня ведения журнала:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Проблемы с установкой журнала

Если ошибка возникает во время установки, установщик будет сообщать только об общем сбое.

Подробный журнал будет сохранен до `/Library/Logs/Microsoft/mdatp/install.log` . Если во время установки вы испытываете проблемы, отправьте нам этот файл, чтобы мы могли помочь диагностировать причину.

## <a name="uninstalling"></a>Uninstalling

Существует несколько способов удалить Microsoft Defender для конечной точки на macOS. Обратите внимание, что, хотя централизованная управляемая удалить доступна на JAMF, она еще недоступна для Microsoft Intune.

### <a name="interactive-uninstallation"></a>Интерактивная деинсталлация

- Open **Finder > приложения**. Правой кнопкой мыши **на кнопку Microsoft Defender для конечной точки > Переместить в корзину**.

### <a name="from-the-command-line"></a>Из командной строки

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a>Настройка из командной строки

Из командной строки можно выполнять важные задачи, такие как управление настройками продуктов и сканы по запросу.

|Group        |Сценарий                                   |Команда                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Конфигурация|Включите/отключите защиту в режиме реального времени           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Конфигурация|Включите/отключите облачную защиту               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Конфигурация|Включите/отключите диагностику продукта            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Конфигурация|Включите/отключите автоматическую отправку образца    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Конфигурация|Добавление имени угрозы в разрешенный список      |`mdatp threat allowed add --name [threat-name]`                                   |
|Конфигурация|Удаление имени угрозы из разрешенного списка |`mdatp threat allowed remove --name [threat-name]`                                |
|Конфигурация|Список всех разрешенных имен угроз              |`mdatp threat allowed list`                                                       |
|Конфигурация|Включив защиту PUA                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Конфигурация|Отключение защиты PUA                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Конфигурация|Включим режим аудита для защиты PUA      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Конфигурация|Включите/отключите passiveMode                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnostics  |Изменение уровня журнала                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnostics  |Создание журналов диагностики                   |`mdatp diagnostic create --path [directory]`                                      |
|Здравоохранение       |Проверка состояния продукта                 |`mdatp health`                                                                    |
|Здравоохранение       |Проверка атрибута spefic product       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Защита   |Сканирование пути                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Защита   |Быстрое сканирование                            |`mdatp scan quick`                                                                |
|Защита   |Полное сканирование                             |`mdatp scan full`                                                                 |
|Защита   |Отмена текущего сканирования по запросу           |`mdatp scan cancel`                                                               |
|Защита   |Запрос обновления сведений о безопасности     |`mdatp definitions update`                                                        |
|EDR          |Добавление тега группы на устройство. EDR теги используются для управления группами устройств. Дополнительные сведения можно получить на сайте /microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Удаление тега группы с устройства               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Добавление группового ID                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Как включить автозаполнение

Чтобы включить автозаполнение в bash, запустите следующую команду и перезапустите сеанс Терминала:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Чтобы включить автозаполнение в zsh:

- Проверьте, включена ли автокомплектация на устройстве:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Если в предыдущей команде не производится какой-либо выход, можно включить автозаполнение с помощью следующей команды:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Запустите следующие команды, чтобы включить автозаполнение для Microsoft Defender для конечной точки на macOS и перезапустить сеанс Терминала:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Клиент Microsoft Defender для каталога карантина конечных точек

`/Library/Application Support/Microsoft/Defender/quarantine/` содержит файлы, которые находятся на `mdatp` карантине. Файлы названы в честь отслеживания угроз. Текущий trackingIds показан с `mdatp threat list` .

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Сведения портала Microsoft Defender для конечных точек

EDR возможности [macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)уже прибыли в блоге Microsoft Defender for Endpoint, где подробно описано, чего ожидать в Центре безопасности конечных точек Microsoft Defender.
