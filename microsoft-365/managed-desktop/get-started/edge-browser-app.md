---
title: Новая версия Microsoft Edge
description: Объясняет, как развертывается и обновляется новый браузер Edge
keywords: браузер, компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822254"
---
# <a name="new-microsoft-edge-app"></a>Новое Microsoft Edge приложение

Новый браузер [Microsoft Edge обеспечивает](https://www.microsoft.com/edge) производительность мирового класса с большей конфиденциальностью, большей производительностью и большей ценностью во время просмотра. компьютеры, управляемые Майкрософт предлагает общедоступный предварительный просмотр развертывания нового браузера Edge в вашей среде.

## <a name="initial-deployment"></a>Начальное развертывание

Для переноса компьютеры, управляемые Майкрософт устройств в новый браузер Microsoft Edge файл билета на поддержку ИТ через портал компьютеры, управляемые Майкрософт. При подаче билета мы развернем канал Edge Stable в тестовой группе, а затем раз в 24 часа развертываем его в каждой последующей группе развертывания. Чтобы приостановить развертывание, задайте другой билет с просьбой о проведении операций.

[Бета-канал](/deployedge/microsoft-edge-channels#beta-channel) также доступен по запросу на представительную проверку в организации. компьютеры, управляемые Майкрософт будет развертывать приложение по мере необходимости в тестовых и первых группах, чтобы все эти пользователи были бета-каналом в дополнение к стабильному каналу. Для всех других пользователей, которым необходим доступ к бета-каналу, добавьте их в группу Современных пользователей бета-версии на рабочем месте **и** установите ее из Корпоративный портал

## <a name="updates-to-microsoft-edge"></a>Обновления для Microsoft Edge

компьютеры, управляемые Майкрософт развертывает стабильный канал [Microsoft Edge,](/deployedge/microsoft-edge-channels#stable-channel) который обновляется автоматически каждые шесть недель. Обновления на канале Stable постепенно [](/deployedge/microsoft-edge-update-progressive-rollout) выкатываются группой Microsoft Edge для обеспечения наилучшего опыта для клиентов. 

[Бета-канал](/deployedge/microsoft-edge-channels#beta-channel) развертывается на устройствах в группах Test и First для представительской проверки в организации. Этот канал полностью поддерживается и обновляется автоматически с новыми функциями примерно каждые шесть недель.

Чтобы убедиться, Microsoft Edge обновления правильно, не Microsoft Edge политики [обновления](/deployedge/microsoft-edge-update-policies).



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Параметры управляется компьютеры, управляемые Майкрософт

компьютеры, управляемые Майкрософт создал по умолчанию набор политик для Microsoft Edge для защиты браузера. Параметры браузера по умолчанию:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge расширения

Базовый уровень безопасности для Microsoft Edge устройств компьютеры, управляемые Майкрософт устанавливает две политики для отключения всех расширений Chrome и обеспечения безопасности пользователей. Чтобы включить и развернуть расширения в вашей среде, Параметры управлять. 

#### <a name="extension-installation-blocklist"></a>Блок-лист установки расширения
**Значение по умолчанию:** Все

компьютеры, управляемые Майкрософт устанавливает эту политику, чтобы не допустить установки расширений Chrome на управляемые конечные точки. Известны риски, связанные с моделью расширения Chromium, включая защиту от потери данных, конфиденциальность и другие риски, которые могут скомпрометировать устройства. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Разрешить родных хостов обмена сообщениями на уровне пользователей (установленных без разрешений администратора)

**Значение по умолчанию:** Отключено

Отключив эту политику, Microsoft Edge использовать только родной хост обмена сообщениями, установленный на уровне системы. Родной хост обмена сообщениями является частью расширений Chrome, которые позволяют браузеру взаимодействовать с другими частями конечной точки пользователя, создавая различные проблемы безопасности.  

### <a name="secure-sockets-layer-tlsssl"></a>Безопасный слой розеток (TLS/SSL)

#### <a name="minimum-tls-version"></a>Минимальная версия TLS

**Значение по умолчанию:** Минимальная поддержка TLS 1.2

Если вы хотите использовать менее безопасный TLS 1.1, для этого можно подать запрос.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Позволяет пользователям перейти со страницы предупреждения SSL

**Значение по умолчанию:** Отключено

Мы не рекомендуем включить этот параметр, так как он позволяет пользователям посещать сайты с ошибками TSL.

### <a name="microsoft-defender-smartscreen"></a>фильтр SmartScreen в Microsoft Defender

#### <a name="configure-windows-defender-smartscreen"></a>Настройка Защитник Windows SmartScreen

**Значение по умолчанию:** Включено

Включено по умолчанию для защиты пользователей.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Защитник Windows Подсказки SmartScreen для сайтов

**Значение по умолчанию:** Включено

Мы не рекомендуем отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и продолжать потенциально вредоносные сайты.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Предотвращение обхода Защитник Windows smartScreen предупреждений о загрузках

**Значение по умолчанию:** Включено

Мы не рекомендуем отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и завершать непроверенные скачивания.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Параметр Adobe Flash по умолчанию

**Значение по умолчанию:** Отключено

Мы не рекомендуем использовать Flash из-за связанных рисков безопасности. Если у вас еще есть процессы, зависят от Flash, установите политику **[PluginsAllowedForUrls,](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** чтобы включить Flash для сайтов, которые в ней нуждаются. Если вы не можете сохранить разрешенный список сайтов для использования Flash, пойдите на запрос изменения, чтобы изменить значение **Click to Play,** что позволяет пользователям выбирать, когда это уместно для запуска Flash.

### <a name="password-manager"></a>Менеджер паролей

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Включить сохранение паролей для диспетчера паролей

**Значение по умолчанию:** Отключено

Диспетчер паролей отключен по умолчанию. Если эта функция включена, отойте запрос на поддержку, и наши инженеры-службы могут включить параметр в вашей среде. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Режим Internet Explorer в Microsoft Edge
Режим IE в Microsoft Edge позволяет с легкостью использовать все нужные организации сайты в одном браузере. Он использует интегрированный Chromium для сайтов, совместимых с Chromium отрисовки, и использует двигатель Trident MSHTML из Internet Explorer 11 (IE11) для сайтов, которые не имеют зависимости от функций IE. [Подробнее](/DeployEdge/edge-ie-mode) 

компьютеры, управляемые Майкрософт режим Internet Explorer для устройств по умолчанию 

#### <a name="internet-explorer-mode-integration"></a>Интеграция режима Internet Explorer
**Значение по умолчанию:** Режим Internet Explorer

По умолчанию устройства должны использовать режим Internet Explorer, но вместо этого их можно настроить для открытия сайтов в окне Автономный internet Explorer 11. Чтобы изменить это поведение, необходимо подать запрос на поддержку.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Добавление сайтов в список Enterprise режима
Чтобы сайты открывали в режиме Internet Explorer, их необходимо включить [в Enterprise сайта.](/DeployEdge/edge-ie-mode-sitelist) Ведение и развертывание списка Enterprise сайта — это ваша ответственность. Подробные сведения см. в [материале Configure using the Configure Enterprise Mode Site List](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Другие параметры

#### <a name="enable-site-isolation-for-every-site"></a>Включить изоляцию сайта для каждого сайта

**Значение по умолчанию:** Включено

Когда эта политика включена, пользователи не могут отказаться от поведения по умолчанию, в котором каждый сайт выполняется в своем собственном процессе.

#### <a name="supported-authentication-schemes"></a>Поддерживаемые схемы проверки подлинности

**Значение по умолчанию:** NTLM, согласование

компьютеры, управляемые Майкрософт не поддерживает базовые или дайджест-схемы проверки подлинности.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Автоматически импортировать данные и параметры другого браузера при первом запуске

**Значение по умолчанию:** Автоматически импортировать все поддерживаемые типы и параметры данных из браузера по умолчанию 

При применении этой политики первый запуск будет пропускать раздел импорта, сводя к минимуму взаимодействие пользователей. Данные браузера из старых версий Microsoft Edge всегда будут безмолвно перенесены при первом запуске, независимо от этого параметра. 


## <a name="settings-you-manage"></a>Параметры управлять

Вы можете развернуть Microsoft Edge параметров, ранее не описанных с помощью профиля Административные шаблоны в Microsoft Intune. Подробные сведения см. [в Microsoft Edge параметры](/deployedge/configure-edge-with-intune)политики с Microsoft Intune. Если вы хотите оценить политику, которая в настоящее время не включена в Microsoft Edge административных шаблонов в Intune, можно использовать настраиваемые параметры для Windows 10 устройств в Intune.

### <a name="enabling-specific-chrome-extensions"></a>Включение определенных расширений Chrome

Административный шаблон предлагает параметр для развертывания определенных расширений Chrome с помощью Microsoft Intune. Вы можете найти его в конфигурации компьютера > Microsoft Edge > расширения > разрешить установку **специальных расширений**.

### <a name="install-extensions-silently"></a>Установка расширений в режиме бесшумной установки

Можно также использовать административный шаблон для Microsoft Edge для установки расширений без оповещения пользователя. Вы можете найти его в **конфигурации компьютера > Microsoft Edge > расширения > управления,** какие расширения устанавливаются молча .

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge политики обновления
Чтобы убедиться, Microsoft Edge обновления правильно, не Microsoft Edge политики [обновления](/deployedge/microsoft-edge-update-policies).

### <a name="other-common-enterprise-policies"></a>Другие общие корпоративные политики

Microsoft Edge предлагает множество других политик. Вот некоторые из наиболее распространенных из них:
 
- [Настройка сайтов в списке Enterprise и режиме IE](/deployedge/edge-ie-mode-sitelist)
- [Настройка параметров страницы запуска, домашней страницы и новых вкладок](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Настройка параметра игры Surf](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Настройка параметров прокси-сервера](/deployedge/microsoft-edge-policies#proxy-server)
