---
title: Развертывание обновлений для Microsoft Defender для конечной точки на Mac
description: Управление обновлениями для Microsoft Defender для конечной точки на Mac в корпоративных средах.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, updates, deploy
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
ms.openlocfilehash: 886195de38856306d69932446eae34212fe4bb0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934505"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Развертывание обновлений для Microsoft Defender для конечной точки на macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки в macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.

Для обновления Microsoft Defender для конечной точки на macOS используется программа с именем Microsoft AutoUpdate (MAU). По умолчанию MAU автоматически проверяет обновления ежедневно, но их можно изменить на еженедельные, ежемесячные или вручную.

![Снимок экрана MAU](images/MDATP-34-MAU.png)

Если вы решите развернуть обновления с помощью средств распространения программного обеспечения, необходимо настроить MAU, чтобы вручную проверять обновления программного обеспечения. Вы можете развернуть настройки, чтобы настроить, как и когда MAU проверяет обновления для macs в организации.

## <a name="use-msupdate"></a>Использование msupdate

MAU включает средство командной строки, называемое *msupdate,* которое предназначено для ИТ-администраторов, чтобы они могли более точно контролировать при применении обновлений. Инструкции по использованию этого средства можно найти в [обновлении Office для Mac с помощью msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).

В MAU идентификатор приложения для Microsoft Defender для конечной точки на macOS *— WDAV00.* Чтобы скачать и установить последние обновления для Microsoft Defender для конечной точки на macOS, выполните следующую команду из окна терминала:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Настройка предпочтений для Microsoft AutoUpdate

В этом разделе описываются наиболее распространенные предпочтения, которые можно использовать для настройки MAU. Эти параметры можно развернуть в качестве профиля конфигурации через консоль управления, которую использует ваше предприятие. Пример профиля конфигурации показан в следующих разделах.

### <a name="set-the-channel-name"></a>Настройка имени канала

Канал определяет тип и частоту обновлений, предлагаемых через MAU. Устройства в `Beta` может попробовать новые функции перед устройствами `Preview` в и `Current` . 

Канал `Current` содержит наиболее стабильную версию продукта.

>[!IMPORTANT]
> До версии Microsoft AutoUpdate 4.29 каналы имели разные имена: 
> 
> - `Beta` был назван `InsiderFast` (Insider Fast)
> - `Preview` был назван `External` (Insider Slow)
> - `Current` был назван `Production`

>[!TIP]
>Чтобы просмотреть новые функции и предоставить ранние отзывы, рекомендуется настроить некоторые устройства в вашем предприятии на `Beta` или `Preview` .

|Section|Значение|
|:--|:--|
| **Домен** | `com.microsoft.autoupdate2` |
| **Key** | ChannelName |
| **Тип данных** | String |
| **Возможные значения** | Бета-версия <br/> Предварительная версия <br/> Current |
|||

>[!WARNING]
>Этот параметр изменяет канал для всех приложений, которые обновляются с помощью Microsoft AutoUpdate. Чтобы изменить канал только для Microsoft Defender для конечной точки на macOS, выполните следующую команду после замены `[channel-name]` на нужный канал:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Установите частоту проверки обновления

Измените, как часто MAU выполняет поиск обновлений.

|Section|Значение|
|:--|:--|
| **Домен** | `com.microsoft.autoupdate2` |
| **Key** | UpdateCheckFrequency |
| **Тип данных** | Целое число |
| **Значение, используемое по умолчанию** | 720 (минут) |
| **Comment** | Это значение устанавливается в минутах. |


### <a name="change-how-mau-interacts-with-updates"></a>Изменение взаимодействия MAU с обновлениями

Измените, как MAU ищет обновления.

|Section|Значение|
|:--|:--|
| **Домен** | `com.microsoft.autoupdate2` |
| **Key** | HowToCheck |
| **Тип данных** | String |
| **Возможные значения** | Вручную <br/> AutomaticCheck <br/> AutomaticDownload |
| **Comment** |  Обратите внимание, что AutomaticDownload будет скачивать и устанавливать безмолвно, если это возможно. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Измените, включена ли кнопка "Проверка обновлений"

Измените, смогут ли местные пользователи щелкнуть параметр "Проверка обновлений" в пользовательском интерфейсе Microsoft AutoUpdate.

|Section|Значение|
|:--|:--|
| **Домен** | `com.microsoft.autoupdate2` |
| **Key** | EnableCheckForUpdatesButton |
| **Тип данных** | Логический |
| **Возможные значения** | True (по умолчанию) <br/> False |


### <a name="disable-insider-checkbox"></a>Отключение почтового ящика Insider

Установите для true, чтобы сделать "Присоединиться к программе инсайдерской службы Office..." checkbox недоступный или серый для пользователей.

|Section|Значение|
|:--|:--|
| **Домен** | `com.microsoft.autoupdate2` |
| **Key** | DisableInsiderCheckbox |
| **Тип данных** | Логический |
| **Возможные значения** | False (по умолчанию) <br/> Верно |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Ограничение телеметрии, отправленной из MAU

Установите для отправки минимальные данные о сердцебиении, отсутствие использования приложений и отсутствие сведений об среде.

|Section|Значение|
|:--|:--|
| **Домен** | `com.microsoft.autoupdate2` |
| **Key** | SendAllTelemetryEnabled |
| **Тип данных** | Логический |
| **Возможные значения** | True (по умолчанию) <br/> False |


## <a name="example-configuration-profile"></a>Пример профиля конфигурации

Следующий профиль конфигурации используется для:
- Поместите устройство в бета-канал
- Автоматическое скачивание и установка обновлений
- Включить кнопку "Проверка обновлений" в пользовательском интерфейсе
- Разрешить пользователям на устройстве зарегистрироваться в каналах Insider

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
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
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Чтобы настроить MAU, вы можете развернуть этот профиль конфигурации из средства управления, которое использует ваше предприятие:
- Из JAMF загрузите этот профиль конфигурации и установите домен preference *на com.microsoft.autoupdate2.*
- В Intune загрузите этот профиль конфигурации и установите имя профиля настраиваемой конфигурации *на com.microsoft.autoupdate2.*

## <a name="resources"></a>Ресурсы

- [msupdate reference](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
