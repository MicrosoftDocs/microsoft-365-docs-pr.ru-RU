---
title: Настройка предпочтений для ATP Защитника Майкрософт для Mac
description: Настройка ATP Microsoft Defender для Mac в корпоративных организациях.
keywords: Microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076933"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a>Настройка предпочтений для Microsoft Defender для конечной точки для Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки для Mac](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>В этой статье содержатся инструкции по набору предпочтений для Microsoft Defender для конечной точки для Mac в корпоративных организациях. Чтобы настроить Microsoft Defender для конечной точки для Mac с помощью интерфейса командной строки, см. [в пункте Ресурсы.](mac-resources.md#configuring-from-the-command-line)

## <a name="summary"></a>Краткое содержание

В корпоративных организациях управление Microsoft Defender для конечной точки для Mac можно с помощью профиля конфигурации, развернутого с помощью одного из нескольких средств управления. Предпочтения, управляемые командой операций безопасности, имеют приоритет над предпочтениями, задав локализованные параметры на устройстве. Изменение предпочтений, задающихся в профиле конфигурации, требует дополнительных привилегий и недоступна пользователям без административных разрешений.

В этой статье описывается структура профиля конфигурации, содержится рекомендуемый профиль, который можно использовать для начала работы, и содержатся инструкции по развертыванию профиля.

## <a name="configuration-profile-structure"></a>Структура профиля конфигурации

Профиль конфигурации — это *файл .plist,* состоящий из записей, идентифицированных ключом (который обозначает имя предпочтения), за которым следует значение, которое зависит от характера предпочтения. Значения могут быть простыми (например, численное значение) или сложными, например вложенным списком предпочтений.

>[!CAUTION]
>Макет профиля конфигурации зависит от используемой консоли управления. В следующих разделах содержатся примеры профилей конфигурации для JAMF и Intune.

Верхний уровень профиля конфигурации включает в себя все продукты и записи для subareas Microsoft Defender для конечной точки, которые подробно объясняются в следующих разделах.

### <a name="antivirus-engine-preferences"></a>Параметры антивирусного двигателя

Раздел *antivirusEngine* профиля конфигурации используется для управления предпочтениями антивирусного компонента Microsoft Defender для конечной точки.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | antivirusEngine |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

#### <a name="enable--disable-real-time-protection"></a>Включить и отключить защиту в режиме реального времени

Укажите, следует ли включить защиту в режиме реального времени, которая сканирует файлы по мере их доступа.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | enableRealTimeProtection |
| **Тип данных** | Логический |
| **Возможные значения** | true (по умолчанию) <br/> false |

#### <a name="enable--disable-passive-mode"></a>Включить и отключить пассивный режим

Укажите, работает ли антивирусный двигатель в пассивном режиме. Пассивный режим имеет следующие последствия: 
- Защита в режиме реального времени отключена
- Включено сканирование по запросу
- Автоматическое устранение угрозы отключено
- Включаем обновления разведки безопасности
- Значок меню состояния скрыт

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | passiveMode |
| **Тип данных** | Логический |
| **Возможные значения** | false (по умолчанию) <br/> true |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 100.67.60 или выше. |

#### <a name="exclusion-merge-policy"></a>Политика слияния исключений

Укажите политику слияния исключений. Это может быть сочетание исключений, определенных администратором и пользователей , или только исключений, определенных `merge` администратором ( `admin_only` ). Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных исключений.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | exclusionsMergePolicy |
| **Тип данных** | String |
| **Возможные значения** | слияние (по умолчанию) <br/> admin_only |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше. |

#### <a name="scan-exclusions"></a>Исключения сканирования

Укажите объекты, исключенные из проверки. Исключения могут быть указаны полными путями, расширениями или именами файлов.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | исключения |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

##### <a name="type-of-exclusion"></a>Тип исключения

Укажите содержимое, исключенное из проверки по типу.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | $type |
| **Тип данных** | String |
| **Возможные значения** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>Путь к исключению контента

Укажите содержимое, исключенное из проверки полным путем файла.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | path |
| **Тип данных** | String |
| **Возможные значения** | допустимые пути |
| **Comments** | Применимо только если *$type* *исключенPath* |

##### <a name="path-type-file--directory"></a>Тип пути (файл / каталог)

Указать, *относится ли* свойство пути к файлу или каталогу. 

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | isDirectory |
| **Тип данных** | Логический |
| **Возможные значения** | false (по умолчанию) <br/> true |
| **Comments** | Применимо только если *$type* *исключенPath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Расширение файла, исключено из сканирования

Укажите содержимое, исключенное из проверки расширением файла.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | расширение |
| **Тип данных** | String |
| **Возможные значения** | допустимые расширения файлов |
| **Comments** | Применимо только если *$type* *исключеноFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Процесс, исключенный из сканирования

Укажите процесс, для которого все действия файла исключены из сканирования. Процесс можно укаварить как по имени (например, так и по полному `cat` пути( `/bin/cat` например).

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | name |
| **Тип данных** | String |
| **Возможные значения** | любая строка |
| **Comments** | Применимо только *если $type* *исключеноFileName* |

#### <a name="allowed-threats"></a>Разрешенные угрозы

Укажите угрозы по имени, которые не заблокированы Защитником для конечной точки для Mac. Эти угрозы будут разрешены для запуска.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | allowedThreats |
| **Тип данных** | Массив строк |

#### <a name="disallowed-threat-actions"></a>Действия с неустановляемой угрозой

Ограничивает действия, которые может принимать локальный пользователь устройства при обнаружении угроз. Действия, включенные в этот список, не отображаются в пользовательском интерфейсе.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | disallowedThreatActions |
| **Тип данных** | Массив строк |
| **Возможные значения** | разрешить (ограничивает пользователей от допуска угроз) <br/> восстановление (ограничивает пользователей от восстановления угроз из карантина) |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше. |

#### <a name="threat-type-settings"></a>Параметры типа угроз

Укажите, как определенные типы угроз обрабатываются Microsoft Defender для конечной точки для Mac.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | threatTypeSettings |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

##### <a name="threat-type"></a>Тип угрозы

Укажите типы угроз.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | ключа |
| **Тип данных** | String |
| **Возможные значения** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>Действие

Укажите, какие действия необходимо принять при обнаружении угрозы типа, указанного в предыдущем разделе. Выберите из следующих вариантов.

- **Аудит:** устройство не защищено от этого типа угрозы, но запись об угрозе регистрируется.
- **Блок:** ваше устройство защищено от этого типа угрозы, и вы будете уведомлены в пользовательском интерфейсе и консоли безопасности.
- **Отключено:** устройство не защищено от этого типа угрозы и ничего не регистрируется.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | значение |
| **Тип данных** | String |
| **Возможные значения** | аудит (по умолчанию) <br/> block <br/> Off |

#### <a name="threat-type-settings-merge-policy"></a>Параметры типа угрозы объединяют политику слияния

Укажите политику слияния для параметров типа угроз. Это может быть сочетание параметров, определенных администратором и определенных пользователем , или только параметров, определенных `merge` администратором ( `admin_only` ). Этот параметр можно использовать, чтобы ограничить местным пользователям определение собственных параметров для различных типов угроз.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | threatTypeSettingsMergePolicy |
| **Тип данных** | String |
| **Возможные значения** | слияние (по умолчанию) <br/> admin_only |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 100.83.73 или выше. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Хранение истории антивирусного сканирования (в днях)

Укажите количество дней, которые сохраняются в истории сканирования на устройстве. Старые результаты сканирования удаляются из истории. Старые карантинные файлы, которые также удаляются с диска.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | scanResultsRetentionDays |
| **Тип данных** | String |
| **Возможные значения** | 90 (по умолчанию). Допустимые значения от 1 дня до 180 дней. |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Максимальное количество элементов в истории антивирусного сканирования

Укажите максимальное количество записей, которые необходимо сохранить в истории сканирования. Записи включают все проверки по запросу, выполняемые в прошлом, и все обнаружения антивирусов.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | scanHistoryMaximumItems |
| **Тип данных** | String |
| **Возможные значения** | 10000 (по умолчанию). Допустимые значения : от 5000 элементов до 15000 элементов. |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 101.07.23 или выше. |

### <a name="cloud-delivered-protection-preferences"></a>Параметры защиты с облачной доставкой

Настройте облачные функции защиты Microsoft Defender для конечной точки для Mac.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | cloudService |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Включить и отключить облачную защиту

Укажите, включить ли облачную защиту устройства или нет. Чтобы повысить безопасность ваших служб, рекомендуется сохранить эту функцию включенной.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | включено |
| **Тип данных** | Логический |
| **Возможные значения** | true (по умолчанию) <br/> false |

#### <a name="diagnostic-collection-level"></a>Уровень диагностической коллекции

Диагностические данные используются для обеспечения безопасности и повышения безопасности Microsoft Defender для конечной точки, обнаружения, диагностики и устранения проблем, а также улучшения продукта. Этот параметр определяет уровень диагностики, отправленной Microsoft Defender для конечной точки в Корпорацию Майкрософт.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | diagnosticLevel |
| **Тип данных** | String |
| **Возможные значения** | необязательный (по умолчанию) <br/> Обязательный |

#### <a name="enable--disable-automatic-sample-submissions"></a>Включить и отключить автоматические отправки образцов

Определяет, отправляются ли подозрительные образцы (которые могут содержать угрозы) в Корпорацию Майкрософт. Вам будет предложено, если в отправленных файлах могут содержаться персональные данные.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | automaticSampleSubmission |
| **Тип данных** | Логический |
| **Возможные значения** | true (по умолчанию) <br/> false |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Включить и отключить автоматические обновления сведении о безопасности

Определяет, устанавливаются ли обновления разведки безопасности автоматически:

|||
|:---|:---|
| **Раздел** | automaticDefinitionUpdateEnabled |
| **Тип данных** | Логический |
| **Возможные значения** | true (по умолчанию) <br/> false |

### <a name="user-interface-preferences"></a>Предпочтения пользовательского интерфейса

Управление предпочтениями пользовательского интерфейса Microsoft Defender для конечной точки для Mac.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | userInterface |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

#### <a name="show--hide-status-menu-icon"></a>Значок меню "Показать/ скрыть состояние"

Укажите, показывать или скрывать значок меню состояния в правом верхнем углу экрана.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | hideStatusMenuIcon |
| **Тип данных** | Логический |
| **Возможные значения** | false (по умолчанию) <br/> true |

#### <a name="show--hide-option-to-send-feedback"></a>Параметр Show/hide для отправки отзывов

Укажите, могут ли пользователи отправлять отзывы в Корпорацию Майкрософт, переехав `Help`  >  `Send Feedback` в .

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | userInitiatedFeedback |
| **Тип данных** | String |
| **Возможные значения** | включено (по умолчанию) <br/> отключено |
| **Comments** | Доступно в Microsoft Defender для конечной точки версии 101.19.61 или выше. |

### <a name="endpoint-detection-and-response-preferences"></a>Параметры обнаружения конечных точек и ответов

Управление предпочтениями компонента обнаружения и ответа конечной точки (EDR) Microsoft Defender для конечной точки для Mac.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | edr |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

#### <a name="device-tags"></a>Теги устройств

Укажите имя тега и его значение. 

- Тег GROUP указывает устройство с указанным значением. Тег отражается на портале на странице устройства и может использоваться для фильтрации и группировки устройств.

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | tags |
| **Тип данных** | Словарь (вложенные предпочтения) |
| **Comments** | В следующих разделах описано содержимое словаря. |

##### <a name="type-of-tag"></a>Тип тега

Указывает тип тега

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | ключа |
| **Тип данных** | String |
| **Возможные значения** | `GROUP` |

##### <a name="value-of-tag"></a>Значение тега

Указывает значение тега

|||
|:---|:---|
| **Домен** | `com.microsoft.wdav` |
| **Раздел** | значение |
| **Тип данных** | String |
| **Возможные значения** | любая строка |

> [!IMPORTANT]  
> - Можно установить только одно значение для каждого типа тегов.
> - Тип тегов уникален и не должен повторяться в одном профиле конфигурации.

## <a name="recommended-configuration-profile"></a>Рекомендуемый профиль конфигурации

Чтобы начать работу, рекомендуется в следующей конфигурации для предприятия воспользоваться всеми функциями защиты, которые предоставляет Microsoft Defender для Endpoint.

Следующий профиль конфигурации (или, в случае JAMF, список свойств, которые можно было бы загрузить в настраиваемый профиль конфигурации параметров) будет:
- Включить защиту в режиме реального времени (RTP)
- Укажите, как обрабатываются следующие типы угроз:
  - **Потенциально нежелательные приложения (PUA)** заблокированы
  - **Архивные бомбы** (файл с высокой скоростью сжатия) проверяются в журналах Microsoft Defender для конечных точек
- Включить автоматические обновления сведении о безопасности
- Включить облачную защиту
- Включить автоматическую отправку образца

### <a name="property-list-for-jamf-configuration-profile"></a>Список свойств для профиля конфигурации JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Профиль Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Пример профиля полной конфигурации

В следующих шаблонах содержатся записи для всех параметров, описанных в этом документе, и они могут использоваться для более сложных сценариев, в которых требуется больше контроля над Microsoft Defender для конечной точки для Mac.

### <a name="property-list-for-jamf-configuration-profile"></a>Список свойств для профиля конфигурации JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Профиль Intune

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Проверка списка свойств

Список свойств должен быть допустимым *файлом .plist.* Это можно проверить, исполнив:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Если файл хорошо сформирован, вышеуказанная команда выводит и возвращает `OK` код выхода `0` . В противном случае отображается ошибка, описываемая проблемой, и команда возвращает код выхода `1` .

## <a name="configuration-profile-deployment"></a>Развертывание профиля конфигурации

После того как вы создали профиль конфигурации для предприятия, вы можете развернуть его через консоль управления, которую использует ваше предприятие. В следующих разделах указаны инструкции по развертыванию этого профиля с помощью JAMF и Intune.

### <a name="jamf-deployment"></a>Развертывание JAMF

На консоли JAMF откройте **профили** конфигурации компьютеров , перейдите в профиль конфигурации, который вы хотите использовать, а затем выберите  >   **настраиваемые параметры.** Создайте запись в качестве домена предпочтений и загрузите ранее произведенный `com.microsoft.wdav` *список .plist.*

>[!CAUTION]
>Необходимо ввести правильный домен предпочтений (); в противном случае параметры не будут `com.microsoft.wdav` распознаны Защитником Майкрософт для конечной точки.

### <a name="intune-deployment"></a>Развертывание Intune

1. Откройте   >  **конфигурацию управления устройством.** Выберите **Управление**  >  **профилями**  >  **Создание профиля**.

2. Выберите имя для профиля. Изменение **platform=macOS на** **тип profile=Custom.** Выберите Настройка.

3. Сохранение списка .plist, выпущенного ранее как `com.microsoft.wdav.xml` .

4. Введите `com.microsoft.wdav` в **качестве настраиваемой конфигурации имя профиля**.

5. Откройте профиль конфигурации и загрузите `com.microsoft.wdav.xml` файл. (Этот файл был создан в шаге 3.)

6. Нажмите кнопку **ОК**.

7. Выберите **управление**  >  **назначениями.** На **вкладке Включить** выберите Назначение всем пользователям & **всех устройств.**

>[!CAUTION]
>Необходимо ввести правильное имя профиля настраиваемой конфигурации; в противном случае эти параметры не будут распознаться Microsoft Defender для конечной точки.

## <a name="resources"></a>Ресурсы

- [Справочник по профилям конфигурации (документация для разработчиков Apple)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
