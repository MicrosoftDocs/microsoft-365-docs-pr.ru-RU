---
title: Новая версия Microsoft Edge
description: Объясняется, как развертывается и обновляется новый браузер Edge
keywords: браузер, компьютер под управлением Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841343"
---
# <a name="new-microsoft-edge-app"></a>Новое приложение Microsoft Edge

Новый браузер [Microsoft Edge](https://www.microsoft.com/edge) обеспечивает производительность мирового класса благодаря большей конфиденциальности, повышению производительности и большему значению при просмотре. Компьютеры, управляемые Майкрософт, предлагают общедоступный предварительный просмотр развертывания нового браузера Edge в вашей среде.

## <a name="initial-deployment"></a>Начальное развертывание

Чтобы перенести компьютеры, управляемые Майкрософт, в новый браузер Microsoft Edge, подайте заявку в службу поддержки ИТ-службы на портале microsoft Managed Desktop Portal. Мы развернем канал Edge Stable в тестовой группе при подаче заявки, а затем развернем его в каждой последующей группе развертывания каждые 24 часа. Чтобы приостановить развертывание, подайте еще один запрос на удержание operations.

Канал [Beta также](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) доступен по запросу на представительную проверку в организации. Компьютеры, управляемые Майкрософт, будут развертывать приложение по мере необходимости в группах "Тестирование" и "Первые группы", чтобы у всех этих пользователей был не только канал Stable, но и канал Beta. Для всех других пользователей, которым нужен доступ к каналу Beta, добавьте их в группу "Современные рабочие места **—** пользователи бета-версии edge" и установите ее с портала компании

## <a name="updates-to-microsoft-edge"></a>Обновления Microsoft Edge

Компьютер под управлением Майкрософт развертывает канал [Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) Microsoft Edge, который обновляется автоматически каждые шесть недель. Обновления в канале Stable последовательно [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) обновляются группой продуктов Microsoft Edge, чтобы обеспечить наилучшее качество работы клиентов. 

Канал [Beta развертывается](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) на устройствах в группах Test и First для представительной проверки в организации. Этот канал полностью поддерживается и автоматически обновляется с помощью новых функций приблизительно каждые шесть недель.

Чтобы убедиться, что Microsoft Edge обновляется правильно, не изменяйте политики [обновления](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Параметры, управляемые компьютером, управляемым Майкрософт

На компьютере, управляемом Майкрософт, создан набор политик по умолчанию для Microsoft Edge для защиты браузера. Параметры браузера по умолчанию:

### <a name="microsoft-edge-extensions"></a>Расширения Microsoft Edge

Базовые параметры безопасности Microsoft Edge на настольных устройствах, управляемых Майкрософт, устанавливают две политики для отключения всех расширений Chrome и защиты пользователей. Чтобы включить и развернуть расширения в своей среде, см. "Параметры", которые вы управляете. 

#### <a name="extension-installation-blocklist"></a>Список блок-блоков установки расширения
**Значение по умолчанию:** Все

Компьютеры, управляемые Майкрософт, устанавливают эту политику, чтобы запретить установку расширений Chrome на управляемых конечных точках. С моделью расширения Chromium связаны известные риски, включая защиту от потери данных, конфиденциальность и другие риски, которые могут нарушить безопасность устройств. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Разрешить точки обмена сообщениями на уровне пользователя (установленные без разрешений администратора)

**Значение по умолчанию:** Отключено

Отключив эту политику, Microsoft Edge будет использовать только ведущие приложения обмена сообщениями, установленные на уровне системы. Ведущие приложения для обмена сообщениями — это часть расширений Chrome, которые позволяют браузеру взаимодействовать с другими частями конечной точки пользователя, создавая различные вопросы безопасности.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Минимальная версия TLS

**Значение по умолчанию:** Минимальная поддерживаемая TLS 1.2

Если вы хотите использовать менее безопасный TLS 1.1, вы можете подать запрос на это.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Позволяет пользователям перейти со страницы предупреждения SSL

**Значение по умолчанию:** Отключено

Не рекомендуется использовать этот параметр, так как он позволяет пользователям посещать сайты с ошибками TSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Настройка Защитник Windows SmartScreen

**Значение по умолчанию:** Включено

Включено по умолчанию для защиты пользователей.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Защитник Windows smartScreen для сайтов

**Значение по умолчанию:** Включено

Мы не рекомендуем отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и продолжать работу с потенциально вредоносными сайтами.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Предотвращение обхода Защитник Windows smartScreen о загрузках

**Значение по умолчанию:** Включено

Не рекомендуется отключать этот параметр, так как это позволит пользователям игнорировать предупреждения и завершать непроверенные загрузки.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Настройка Adobe Flash по умолчанию

**Значение по умолчанию:** Отключено

Не рекомендуется использовать Flash из-за связанных с ним рисков безопасности. Если у вас по-прежнему есть процессы, которые зависят от Flash, установите политику **[PluginsAllowedForUrls,](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** чтобы включить Flash для сайтов, которые в ней нуждаются. Если вы не можете сохранить список разрешенных сайтов для использования Flash, подайте запрос на изменение значения на "Нажми и играй", что позволяет пользователям выбирать, когда следует запускать Flash.

### <a name="password-manager"></a>Диспетчер паролей

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Включить сохранение паролей в диспетчере паролей

**Значение по умолчанию:** Отключено

Не рекомендуется разрешать пользователям сохранять пароли на своих устройствах.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Режим Internet Explorer в Microsoft Edge
Режим IE в Microsoft Edge позволяет с легкостью использовать все нужные организации сайты в одном браузере. Он использует интегрированный механизм Chromium для сайтов, совместимых с механизмом отрисовки Chromium, и механизм Trident MSHTML из Internet Explorer 11 (IE11) для сайтов, которые не имеют зависимостей от функциональности IE. [Подробнее] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Компьютер под управлением Майкрософт включает режим Internet Explorer для устройств по умолчанию 

#### <a name="internet-explorer-mode-integration"></a>Интеграция режима Internet Explorer
**Значение по умолчанию:** Режим Internet Explorer

По умолчанию устройства настроены на использование режима Internet Explorer, но вместо этого их можно настроить на открытие сайтов в автономных окнах Internet Explorer 11. Чтобы изменить это поведение, подав запрос в службу поддержки.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Добавление сайтов в список сайтов в режиме предприятия
Чтобы сайты открывали в режиме Internet Explorer, их необходимо включить в список [корпоративных сайтов.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist) За обслуживание и развертывание списка корпоративных сайтов отвечаете вы. Подробные сведения [см. в настройках с помощью](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy) политики "Настройка списка сайтов в режиме предприятия"

### <a name="other-settings"></a>Другие параметры

#### <a name="enable-site-isolation-for-every-site"></a>Включить изоляцию сайта для каждого сайта

**Значение по умолчанию:** Включено

Если эта политика включена, пользователи не могут отказаться от поведения по умолчанию, в котором каждый сайт выполняется в своем собственном процессе.

#### <a name="supported-authentication-schemes"></a>Поддерживаемые схемы проверки подлинности

**Значение по умолчанию:** NTLM, согласование

Компьютеры, управляемые Майкрософт, не поддерживают схемы базовой или дайджест-проверки подлинности.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Автоматически импортировать данные и параметры другого браузера при первом запуске

**Значение по умолчанию:** Автоматически импортировать все поддерживаемые типы данных и параметры из браузера по умолчанию 

При применении этой политики интерфейс первого запуска пропускает раздел импорта, минимизируя взаимодействие с пользователем. Данные браузера из более старых версий Microsoft Edge всегда будут автоматически перенесены при первом запуске независимо от этого параметра. 


## <a name="settings-you-manage"></a>Параметры, которые вы управляете

Вы можете развернуть любые параметры Microsoft Edge, не описанные ранее, с помощью профиля административных шаблонов в Microsoft Intune. Подробные сведения см. в настройке параметров политики [Microsoft Edge с помощью Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune) Если вы хотите оценить политику, которая в настоящее время не включена в административные шаблоны Microsoft Edge в Intune, можно использовать настраиваемые параметры для устройств с Windows 10 в Intune.

### <a name="enabling-specific-chrome-extensions"></a>Включение определенных расширений Chrome

Административный шаблон предлагает параметр для развертывания определенных расширений Chrome с помощью Microsoft Intune. Его можно найти в конфигурации **компьютера > Microsoft Edge > extensions > Allow Specific Extensions to be installed**.

### <a name="install-extensions-silently"></a>Установка расширений в тихом режиме

Вы также можете использовать административный шаблон, чтобы настроить Microsoft Edge на установку расширений, не оповещая пользователя. Его можно найти в конфигурации **компьютера > Microsoft Edge > Extensions > Control,** какие расширения устанавливаются автоматически.

### <a name="microsoft-edge-update-policies"></a>Политики обновления Microsoft Edge
Чтобы убедиться, что Microsoft Edge обновляется правильно, не изменяйте политики [обновления](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.

### <a name="other-common-enterprise-policies"></a>Другие распространенные корпоративные политики

Microsoft Edge предлагает множество других политик. Вот некоторые из наиболее распространенных:
 
- [Настройка сайтов в списке корпоративных сайтов и режиме IE](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Настройка параметров страницы запуска, домашней страницы и новой вкладки](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Настройка параметра игры "Просмотр"](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Настройка параметров прокси-сервера](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

