---
title: Технические сведения о шифровании
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Узнайте о различных сертификатах, технологиях и наборах шифров TLS, используемых для шифрования в Office 365 и Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e6b001b308519fb35e0cc835ac03fb4b27db260
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233145"
---
# <a name="technical-reference-details-about-encryption"></a>Технические сведения о шифровании

В этой статье вы узнаете о сертификатах, технологиях и наборах шифров TLS, используемых для шифрования [в Office 365.](encryption.md) В этой статье также приводится подробная информация о запланированных отзывах.
  
- Если вы ищете общие сведения, см. ["Шифрование" в Office 365.](encryption.md)
- Если вы ищете сведения о настройке, см. сведения [о настройке шифрования в Office 365 корпоративный.](set-up-encryption.md)
- Сведения о наборах шифров, поддерживаемых определенными версиями Windows, см. в подголовке ["Пакеты шифрования" в TLS/SSL (Schannel SSP).](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Владение и управление сертификатами Microsoft Office 365

Вам не нужно приобретать или обслуживать сертификаты для Office 365. Вместо этого Office 365 использует собственные сертификаты.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Текущие стандарты шифрования и запланированное амортизации

Чтобы обеспечить наилучшее в своем классе шифрование, Office 365 регулярно проверяет поддерживаемые стандарты шифрования. Иногда старые стандарты устарели по мере того, как они устарели и стали менее безопасными. В этой статье описываются поддерживаемые в настоящее время наборы шифров, а также другие стандарты, а также сведения о планируемом отзыве лицензий.

## <a name="fips-compliance-for-office-365"></a>Соответствие требованиям FIPS для Office 365

Все наборы шифров, поддерживаемые Office 365, используют алгоритмы, допустимые в FIPS 140-2. Office 365 наследует проверки FIPS от Windows (через Schannel). Сведения о Schannel см. в наборах [шифров в TLS/SSL (Schannel SSP).](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Версии протокола TLS, поддерживаемые Office 365

TLS и SSL, которые были до TLS, — это криптографические протоколы, которые безопасны для связи по сети с помощью сертификатов безопасности для шифрования подключения между компьютерами. Office 365 поддерживает TLS версии 1.2 (TLS 1.2).

TLS версии 1.3 (TLS 1.3) в настоящее время не поддерживается.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Поддержка сноса TLS 1.0 и 1.1

Office 365 перестал поддерживать TLS 1.0 и 1.1 31 октября 2018 г. Мы завершили отключение TLS 1.0 и 1.1 в средах GCC High и DoD. Мы начали отключать TLS 1.0 и 1.1 для сред Worldwide и GCC с 15 октября 2020 г. и продолжим работу в течение следующих недель и месяцев.

Для обеспечения безопасного подключения к службам Office 365 и Microsoft 365 все сочетания клиент-сервер и браузер-сервер используют TLS 1.2 и современные наборы шифров. Возможно, придется обновить определенные сочетания клиент-сервер и браузер-сервер. Сведения об изменении см. в подготовии к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Поддержка 3DES не поддерживается

С 31 октября 2018 г. Office 365 больше не поддерживает использование наборов шифров 3DES для связи с Office 365. В частности, Office 365 больше не поддерживает набор TLS_RSA_WITH_3DES_EDE_CBC_SHA шифров. С 28 февраля 2019 г. этот набор шифров отключен в Office 365. Клиенты и серверы, которые взаимодействуют с Office 365, должны поддерживать один или несколько поддерживаемых шифров. Список поддерживаемых шифров см. в наборах [шифров TLS, поддерживаемых Office 365.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Прекращение поддержки сертификата SHA-1 в Office 365

С июня 2016 г. Office 365 больше не принимает сертификат SHA-1 для исходящие или входящие подключения. Используйте SHA-2 (безопасный алгоритм hash Algorithm 2) или более надежный алгоритм в цепочке сертификатов.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Наборы шифров TLS, поддерживаемые в Office 365

Протокол TLS использует *наборы* шифров , коллекции алгоритмов шифрования, для создания безопасных подключений. Office 365 поддерживает наборы шифров, перечисленные в следующей таблице. В таблице перечислены наборы шифров по упорядочению, а самый мощный набор шифров указан первым.

Office 365 отвечает на запрос на подключение, сначала пытается подключиться с использованием наиболее безопасного набора шифров. Если подключение не работает, Office 365 пытается использовать второй наиболее безопасный набор шифров в списке и т. д. Служба продолжает оставаться в списке, пока подключение не будет принято. Аналогичным образом, когда Office 365 запрашивает подключение, служба получения выбирает, будет ли использоваться TLS и какой набор шифров использовать.

> [!IMPORTANT]
> Следует помнить, что версии TLS являются нерекоместойными и не следует использовать их там, где доступны более новые версии.  TLS 1.3 в настоящее время не поддерживается. Если устаревшие службы не требуют TLS 1.0 или 1.1, их следует отключить.

| Набор шифров | Ключевой алгоритм и сила обмена ключами | Forward Secrecy | Шифр и сила | Алгоритм проверки подлинности |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Да <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Да <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Да <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Да <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Да <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Да <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Нет <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Нет <br/> |AES/256 <br/>|RSA/112 <br/> |

Эти наборы шифров поддерживали протоколы TLS 1.0 и 1.1 до даты их сноса. Для сред GCC High и DoD, которые устарели 15 января 2020 г., а для сред Worldwide и GCC эта дата была 15 октября 2020 г.

| Протоколы | Имя набора шифров | Алгоритм обмена ключами/сила | Поддержка forward Secrecy | Алгоритм и сила проверки подлинности | Шифр и сила |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Да  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Да  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Нет  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Нет  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Нет   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Нет   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Статьи по теме

[Наборы шифров TLS в Windows 10 версии 1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Шифрование в Office 365](encryption.md)
  
[Настройка шифрования в Office 365 корпоративный](set-up-encryption.md)
  
[Реализация Schannel TLS 1.0 в обновлении состояния безопасности Windows: 24 ноября 2015 г.](https://support.microsoft.com/kb/3117336)
  
[Улучшения шифрования TLS/SSL (ИТ-центр Windows)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Подготовка к TLS 1.2 в Office 365 и Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
