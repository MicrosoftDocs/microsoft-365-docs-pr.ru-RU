---
title: Отключение TLS 1.0 и 1.1 для Microsoft 365
description: Описывает TLS 1.0 и 1.1 амортизации и отключения для Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332682"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Отключение TLS 1.0 и 1.1 для Microsoft 365

> [!IMPORTANT]
> Мы временно прекратили отключение TLS 1.0 и 1.1 для коммерческих клиентов из-за COVID-19. По мере корректировки цепочек поставок и открытия некоторых стран 15 октября 2020 г. мы перезапустили запуск TLS 1.2. Выкатка будет продолжена в течение следующих недель и месяцев.

С 31 октября 2018 г. протоколы безопасности транспортного слоя (TLS) 1.0 и 1.1 не будут Microsoft 365 службы. Эффект для конечных пользователей минимальный. Это изменение было опубликовано более двух лет, с первым публичным объявлением, сделанным в декабре 2017 г. Эта статья предназначена только для Office 365 локального клиента по отношению к службе Office 365, но также может применяться к локальным TLS-вопросам с Office и Office Online Server/Office веб-приложениями.

Для SharePoint и OneDrive необходимо обновить и настроить .NET для поддержки TLS 1.2. Сведения см. [в том, как включить TLS 1.2 для клиентов.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Office 365 и TLS обзор

Клиент Office использует веб-службу Windows (WINHTTP) для отправки и получения трафика по протоколам TLS. Клиент Office TLS 1.2, если веб-служба локального компьютера может использовать TLS 1.2. Все Office могут использовать протоколы TLS, так как протоколы TLS и SSL являются частью операционной системы и не являются Office клиентом.

### <a name="on-windows-8-and-later-versions"></a>В Windows 8 и более поздних версиях

По умолчанию протоколы TLS 1.2 и 1.1 доступны, если не настроены сетевые устройства для отказа от трафика TLS 1.2.

### <a name="on-windows-7"></a>На Windows 7

Протоколы TLS 1.1 и 1.2 недоступны без обновления [KB 3140245.](https://support.microsoft.com/help/3140245) Обновление решает эту проблему и добавляет следующий под ключ реестра:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 пользователей, которые не имеют этого обновления, по 31 октября 2018 г. [В KB 3140245](https://support.microsoft.com/help/3140245) есть сведения о том, как изменить параметры WINHTTP, чтобы включить протоколы TLS.

#### <a name="more-information"></a>Дополнительные сведения

Значение ключа реестра **DefaultSecureProtocols,** описываемого в статье KB, определяет, какие сетевые протоколы можно использовать:

|Значение DefaultSecureProtocols|Включен протокол|
|-|-|
|0x00000008|Включить протокол SSL 2.0 по умолчанию|
|0x00000020|Включить протокол SSL 3.0 по умолчанию|
|0x00000080|Включить протокол TLS 1.0 по умолчанию|
|0x00000200|Включить протокол TLS 1.1 по умолчанию|
|0x00000800|Включить протокол TLS 1.2 по умолчанию|

## <a name="office-clients-and-tls-registry-keys"></a>Office клиентов и ключей реестра TLS

Вы можете обратиться к [KB 4057306 Подготовка](https://support.microsoft.com/help/4057306)к обязательному использованию TLS 1.2 в Office 365 . Это общая статья для ИТ-администраторов и это официальная документация об изменении TLS 1.2.

В следующей таблице показаны соответствующие ключевые значения реестра в Office 365 после 31 октября 2018 г.

|Включенные протоколы для Office 365 службы после 31 октября 2018 г.|Hexadecimal value|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Не используйте протоколы SSL 2.0 и 3.0, которые также можно установить с помощью **ключа DefaultSecureProtocols.** Протоколы SSL 2.0 и 3.0 считаются устаревшими и небезопасными. Лучше всего прекратить использование SSL 2.0 и SSL 3.0, хотя решение об этом в конечном счете зависит от того, что наилучшим образом соответствует вашим потребностям продукта. Дополнительные сведения об уязвимостях SSL 3.0 можно найти в [KB 3009008.](https://support.microsoft.com/help/3009008)

Вы можете использовать калькулятор Windows по умолчанию в режиме Программист, чтобы настроить те же ключевые значения реестра ссылок. Дополнительные сведения см. в обновлении [KB 3140245, чтобы включить TLS 1.1 и TLS 1.2](https://support.microsoft.com/help/3140245)в качестве безопасных протоколов по умолчанию в WinHTTP в Windows .

Независимо от Windows обновления 7[(KB 3140245)](https://support.microsoft.com/help/3140245)установлено или нет, ключ реестра defaultSecureProtocols не присутствует и должен быть добавлен вручную или через объект групповой политики (GPO). То есть, если вам не придется настраивать, какие безопасные протоколы включены или ограничены, этот ключ не требуется. Требуется только обновление Windows 7 SP1[(KB 3140245).](https://support.microsoft.com/help/3140245)

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Обновление и настройка платформа .NET Framework для поддержки TLS 1.2

Чтобы использовать TLS 1.2, необходимо обновить приложения, которые Microsoft 365 API через TLS 1.0 или TLS 1.1. .NET 4.5 по умолчанию для TLS 1.1. Чтобы обновить конфигурацию .NET, см. в руб. Как включить безопасность транспортного слоя [(TLS) 1.2 для клиентов.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения см. в статью Подготовка к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

## <a name="references"></a>Ссылки

Следующие ресурсы предоставляют рекомендации, которые помогут убедиться, что ваши клиенты используют TLS 1.2 или более поздней версии, и отключить TLS 1.0 и 1.1:

- Клиенты Windows 7, которые подключаются к Office 365, должны убедиться, что TLS 1.2 является безопасным протоколом по умолчанию в WinHTTP в Windows. Дополнительные сведения см. в [kB 3140245 . Обновление, чтобы включить TLS 1.1 и TLS 1.2](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)в качестве безопасных протоколов по умолчанию в WinHTTP в Windows .
- Чтобы решить проблему слабого использования TLS путем удаления зависимостей TLS 1.0 и 1.1, см. в поддержку [TLS 1.2 в Microsoft.](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)
- [Новые функциональные возможности IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) упрощают поиск клиентов в [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) и [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334), которые подключаются к службе с помощью слабых протоколов безопасности.
- Дополнительные сведения о том, как решить проблему [TLS 1.0.](https://www.microsoft.com/download/details.aspx?id=55266)
- Общие сведения о подходе к безопасности см. в [Центре управления безопасностью Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Подготовка к отключению TLS 1.0/1.1 - Office 365 Skype для бизнеса](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Рекомендации по TLS Exchange Server, часть 1: Подготовка к TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Рекомендации по TLS Exchange Server, часть 2: Включение TLS 1.2 и определение клиентов, которые не используют его](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Рекомендации по TLS Exchange Server, часть 3: Выключение TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Включение поддержки TLS 1.1 и TLS 1.2 в Office Online Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

