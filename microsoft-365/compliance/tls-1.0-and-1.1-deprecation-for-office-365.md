---
title: Отключение TLS 1.0 и 1.1 для Microsoft 365
description: Описывается отключение и отключение TLS 1.0 и 1.1 для Microsoft 365.
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
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233101"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Отключение TLS 1.0 и 1.1 для Microsoft 365

> [!IMPORTANT]
> Мы временно остановили отключение TLS 1.0 и 1.1 для коммерческих клиентов из-за COVID-19. По мере того как цепочки поставок скорректированы и некоторые страны открывают их, 15 октября 2020 г. мы перезапустили обязательное исполнение TLS 1.2. Выкат будет продолжен в течение следующих недель и месяцев.

С 31 октября 2018 г. протоколы TLS 1.0 и 1.1 являются неподготовленными для службы Microsoft 365. Эффект для конечных пользователей минимальный. Это изменение было опубликовано в течение двух лет с первым общедоступным объявлением, сделанным в декабре 2017 г. Эта статья предназначена только для локального клиента Office 365 относительно службы Office 365, но также может применяться к локальным вопросам TLS в Office и Office Online Server/Office Web Apps.

Для SharePoint и OneDrive необходимо обновить и настроить .NET для поддержки TLS 1.2. Сведения см. в [том, как включить TLS 1.2 на клиентах.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Обзор Office 365 и TLS

Клиент Office использует веб-службу Windows (WINHTTP) для отправки и получения трафика по протоколам TLS. Клиент Office может использовать TLS 1.2, если веб-служба локального компьютера может использовать TLS 1.2. Все клиенты Office могут использовать протоколы TLS, так как протоколы TLS и SSL являются частью операционной системы и не являются специфическими для клиента Office.

### <a name="on-windows-8-and-later-versions"></a>В Windows 8 и более поздних версиях

По умолчанию протоколы TLS 1.2 и 1.1 доступны, если сетевые устройства не настроены на отклонение трафика TLS 1.2.

### <a name="on-windows-7"></a>В Windows 7

Протоколы TLS 1.1 и 1.2 недоступны без обновления [KB 3140245.](https://support.microsoft.com/help/3140245) Обновление решает эту проблему и добавляет следующий под ключ реестра:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> С 31 октября 2018 г. затронут пользователи Windows 7, у которых нет этого обновления. [В KB 3140245](https://support.microsoft.com/help/3140245) есть сведения об изменении параметров WINHTTP, чтобы включить протоколы TLS.

#### <a name="more-information"></a>Дополнительные сведения

Значение ключа реестра **DefaultSecureProtocols,** описанного в статье КБ, определяет, какие сетевые протоколы можно использовать:

|Значение DefaultSecureProtocols|Протокол включен|
|-|-|
|0x00000008|Включить протокол SSL 2.0 по умолчанию|
|0x00000020|Включить протокол SSL 3.0 по умолчанию|
|0x00000080|Включить протокол TLS 1.0 по умолчанию|
|0x00000200|Включить протокол TLS 1.1 по умолчанию|
|0x00000800|Включить протокол TLS 1.2 по умолчанию|

## <a name="office-clients-and-tls-registry-keys"></a>Клиенты Office и ключи реестра TLS

Вы можете обратиться к [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306). Это общая статья для ИТ-администраторов и ее официальной документации об изменении TLS 1.2.

В следующей таблице показаны соответствующие значения ключей реестра в клиентах Office 365 после 31 октября 2018 г.

|Включенные протоколы для службы Office 365 после 31 октября 2018 г.|Hexadecimal value|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Не используйте протоколы SSL 2.0 и 3.0, которые также можно настроить с помощью ключа **DefaultSecureProtocols.** Протоколы SSL 2.0 и 3.0 считаются устаревшими и небезопасными протоколами. Лучше всего прекратить использование SSL 2.0 и SSL 3.0, хотя решение об этом в конечном итоге зависит от того, что лучше всего соответствует потребностям вашего продукта. Дополнительные сведения об уязвимостях SSL 3.0 можно найти в [KB 3009008.](https://support.microsoft.com/help/3009008)

Вы можете использовать калькулятор Windows по умолчанию в режиме программиста, чтобы настроить одинаковые значения эталонного ключа реестра. Дополнительные сведения см. в обновлении [KB 3140245, чтобы включить протоколы TLS 1.1 и TLS 1.2](https://support.microsoft.com/help/3140245)в качестве протоколов безопасности по умолчанию в WinHTTP в Windows.

Независимо от того, установлено ли обновление Windows[7 (KB 3140245),](https://support.microsoft.com/help/3140245)подразрядный ключ реестра DefaultSecureProtocols не существует и должен быть добавлен вручную или с помощью объекта групповой политики (GPO). То есть, если вам не нужно настраивать протоколы безопасности, которые включены или ограничены, этот ключ не требуется. Вам потребуется только обновление Windows 7 с sp1[(KB 3140245).](https://support.microsoft.com/help/3140245)

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Обновление и настройка .NET Framework для поддержки TLS 1.2

Вам потребуется обновить приложения, которые звонят API Microsoft 365 по TLS 1.0 или TLS 1.1, чтобы использовать TLS 1.2. .NET 4.5 по умолчанию TLS 1.1. Чтобы обновить конфигурацию .NET, узнайте, как включить [TLS 1.2 на клиентах.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>Дополнительные сведения

Дополнительные сведения см. в подготовии к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
