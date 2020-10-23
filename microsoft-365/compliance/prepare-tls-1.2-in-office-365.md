---
title: Подготовка к TLS 1.2 в Office 365 и Office 365 GCC
description: Как подготовиться к использованию TLS 1.2 для всех сочетаний клиент-сервер и браузер-сервер в Office 365 после отключения поддержки TLS 1.0 и 1.1.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 4cc1fc739ee7fbcc4b976ae6e3f220713a53a007
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681661"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Подготовка к TLS 1.2 в Office 365 и Office 365 GCC

## <a name="summary"></a>Аннотация

Чтобы обеспечить лучшее в своем классе шифрование для наших пользователей, Майкрософт планирует прекратить поддержку версий протокола TLS 1.0 и 1.1 в Office 365 и Office 365 GCC. Мы понимаем, что безопасность ваших данных важна, и мы стремимся к прозрачности изменений, которые могут повлиять на использование службы TLS.

[Внедрение Microsoft](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) TLS 1.0 не имеет известных уязвимостей безопасности. Однако в связи с вероятностью атак на протокол в будущем и других уязвимостей TLS, мы прекращаем поддержку TLS 1.0 и 1.1 в Microsoft Office 365 и Office 365 GCC.

Для получения информации о том, как удалить зависимости TLS 1.0 и 1.1, см. следующий технический документ: [Решение проблемы TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).

## <a name="more-information"></a>Дополнительная информация

Мы уже начали отключение TLS 1.0 и 1.1 с января 2020 года. Любые клиенты, устройства или службы, которые подключаются к Office 365 через TLS 1.0 или 1.1 в наших экземплярах DoD или GCC High, не поддерживаются. Для наших коммерческих клиентов Office 365, устаревшие протоколы TLS 1,0 и 1,1 начнутся 15 октября, 2020 и выпуск будут продолжаться на следующих неделях и месяцах. 

Необходимо убедиться в том, что все сочетания клиент-сервер и браузер-сервер используют протокол TLS 1.2 (или более поздней версии) для поддержки подключения к службам Office 365. Возможно, придется обновить определенные сочетания клиент-сервер и браузер-сервер.

Следующие клиенты не могут использовать TLS 1.2. Обновите клиенты, чтобы обеспечить непрерывный доступ к службе.

- Android 4.3 и более ранние версии
- Firefox 5.0 и более ранние версии:
- Internet Explorer 8-10 на Windows 7 и более ранние версии
- Internet Explorer 10 на Windows Phone 8
- Safari 6.0.4/OS X10.8.4 и более ранние версии

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 для Microsoft Teams Rooms и Surface Hub

Комнаты Microsoft Teams (ранее известны как Skype Room System V2 SRS V2) поддерживают TLS 1.2 с декабря 2018 года. Мы рекомендуем устройствам Rooms иметь версию приложения Microsoft Teams Rooms 4.0.64.0 или более позднюю. Дополнительные сведения см. в [Заметках о выпуске](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note). Изменения обратно и прямо совместимы.

Surface Hub выпустила поддержку TLS 1.2 в мае 2019 года.

Поддержка TLS 1.2 для продуктов Microsoft Teams Rooms и Surface Hub также требует следующих изменений кода на стороне сервера:

- Изменения в сервере Skype для бизнеса Online были введены в действие в апреле 2019 года. Теперь Skype для бизнеса Online поддерживает подключение комнат Microsoft Teams и устройств Surface Hub с использованием TLS 1.2.
- Клиенты Skype для бизнеса Server должны установить накопительное обновление (CU), чтобы использовать TLS 1.2 для Teams Rooms Systems и Surface Hub.

  - Для Skype для бизнеса Server 2015 CU9 уже выпущен в мае 2019 года.
  - Для Skype для бизнеса Server 2019 накопительное обновление 1 (CU1) ранее было запланировано на апрель 2019 года, но отложено до июня 2019 года.

  > [!NOTE]
  > Клиенты локальной службы Skype для бизнеса не должны отключать TLS 1.0 / 1.1 перед установкой определенных накопительных обновлений для Skype для бизнеса Server.

Если используется локальная инфраструктура для гибридных сценариев или служб федерации Active Directory, убедитесь, что инфраструктура поддерживает как входящие, так и исходящие подключения, использующие TLS 1.2.

## <a name="references"></a>Ссылки

Следующие ресурсы содержат руководство по использованию протокола TLS 1.2 или более поздней версии и для отключения TLS 1.0 и 1.1.

- Клиенты Windows 7, которые подключаются к Office 365, должны убедиться, что TLS 1.2 является безопасным протоколом по умолчанию в WinHTTP в Windows. Дополнительные сведения см. в статье [базы знаний 3140245 - Обновление для включения TLS 1.1 и TLS 1.2 в качестве стандартных протоколов по умолчанию в WinHTTP в Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- Чтобы начать адресацию слабого использования TLS, удалив зависимости TLS 1.0 и 1.1, см. поддержку [TLS 1.2 в Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [Новые функциональные возможности IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) упрощают поиск клиентов в [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) и [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334), которые подключаются к службе с помощью слабых протоколов безопасности.
- Получите дополнительные сведения о [решении проблемы с TLS 1,0](https://www.microsoft.com/download/details.aspx?id=55266).
- Общие сведения о подходе к безопасности см. в [Центре управления безопасностью Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Подготовка к отключению TLS 1.0/1.1 - Office 365 Skype для бизнеса](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Рекомендации по TLS Exchange Server, часть 1: Подготовка к TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Рекомендации по TLS Exchange Server, часть 2: Включение TLS 1.2 и определение клиентов, которые не используют его](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Рекомендации по TLS Exchange Server, часть 3: Выключение TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Включение поддержки TLS 1.1 и TLS 1.2 в Office Online Server](https://docs.microsoft.com/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
