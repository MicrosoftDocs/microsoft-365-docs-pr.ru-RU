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
description: Узнайте о различных наборах шифров сертификатов, технологий и безопасности транспортных слоев (TLS), используемых для шифрования в Office 365 и Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919355"
---
# <a name="technical-reference-details-about-encryption"></a>Технические сведения о шифровании

В этой статье вы узнаете о сертификатах, технологиях и шифрах TLS, используемых для шифрования [в Office 365.](encryption.md) В этой статье также приводится подробная информация о планируемых амортизации.
  
- Если вы ищете сведения об обзоре, см. в руб. [Шифрование в Office 365.](encryption.md)
- Если вы ищете сведения о настройке, см. в руб. [Настройка шифрования в Office 365 Enterprise.](set-up-encryption.md)
- Сведения о наборах шифров, поддерживаемых определенными версиями Windows, см. в ссылке [Cipher Suites in TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Владение и управление сертификатами Microsoft Office 365

Вам не нужно приобретать или поддерживать сертификаты для Office 365. Вместо этого Office 365 использует собственные сертификаты.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Текущие стандарты шифрования и планируемые амортизации

Чтобы обеспечить наилучшее шифрование в классе, Office 365 регулярно проверяет поддерживаемые стандарты шифрования. Иногда старые стандарты устарели и становятся менее безопасными. В этой статье описываются поддерживаемые в настоящее время наборы шифров и другие стандарты и сведения о планируемых амортизации.

## <a name="fips-compliance-for-office-365"></a>Соответствие требованиям FIPS для Office 365

Все наборы шифров, поддерживаемые Office 365, используют алгоритмы, приемлемые в соответствии с FIPS 140-2. Office 365 наследует проверки FIPS из Windows (через Schannel). Сведения о Schannel см. в ссылке [Cipher Suites in TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Версии протокола TLS, поддерживаемые Office 365

TLS и SSL, которые были до TLS, являются криптографическими протоколами, которые обеспечивает связь через сеть с помощью сертификатов безопасности для шифрования подключения между компьютерами. Office 365 поддерживает TLS версии 1.2 (TLS 1.2).

TLS версия 1.3 (TLS 1.3) в настоящее время не поддерживается.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Поддержка амортизации TLS 1.0 и 1.1

Office 365 перестал поддерживать TLS 1.0 и 1.1 31 октября 2018 г. Мы завершили отключение TLS 1.0 и 1.1 в средах GCC High и DoD. Мы начали отключение TLS 1.0 и 1.1 для сред worldwide и GCC начиная с 15 октября 2020 г. И в течение следующих недель и месяцев мы будем продолжать работу.

Для обеспечения безопасного подключения к службам Office 365 и Microsoft 365 все комбинации клиент-сервер и браузер-сервер используют TLS 1.2 и современные наборы шифров. Возможно, придется обновить определенные сочетания клиент-сервер и браузер-сервер. Сведения о том, как это изменение влияет на вас, см. в статью Подготовка к обязательному использованию [TLS 1.2 в Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Откат поддержки для 3DES

С 31 октября 2018 г. Office 365 больше не поддерживает использование шифров 3DES для связи с Office 365. В частности, Office 365 больше не поддерживает набор TLS_RSA_WITH_3DES_EDE_CBC_SHA шифров. С 28 февраля 2019 г. этот набор шифров отключен в Office 365. Клиенты и серверы, которые взаимодействуют с Office 365, должны поддерживать один или несколько поддерживаемых шифров. Список поддерживаемых шифров см. в списке [наборов шифров TLS, поддерживаемых Office 365.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Прекращение поддержки сертификата SHA-1 в Office 365

С июня 2016 г. Office 365 больше не принимает сертификат SHA-1 для исходящие или входящие подключения. Используйте SHA-2 (Secure Hash Algorithm 2) или более надежный алгоритм хаширования в цепочке сертификатов.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Наборы шифров TLS, поддерживаемые Office 365

TLS использует *наборы шифров,* коллекции алгоритмов шифрования для создания безопасных подключений. Office 365 поддерживает наборы шифров, перечисленные в следующей таблице. В таблице перечислены наборы шифров в порядке прочности, а самый сильный набор шифров указан в первую очередь.

Office 365 отвечает на запрос на подключение, сначала пытаясь подключиться с помощью наиболее безопасного набора шифров. Если подключение не работает, Office 365 пробует второй наиболее безопасный набор шифров в списке и т. д. Служба продолжает оставаться в списке до тех пор, пока подключение не будет принято. Кроме того, когда Office 365 запрашивает подключение, служба получения выбирает, будет ли использоваться TLS и какой набор шифров использовать.

> [!IMPORTANT]
> Следует помнить, что версии TLS обесценяются и  что не следует использовать их там, где доступны более новые версии. TLS 1.3 в настоящее время не поддерживается. Если устаревшие службы не требуют TLS 1.0 или 1.1, их следует отключить.

| Набор шифров | Алгоритм обмена ключами/прочность | Секретность форварда | Cipher/strength | Алгоритм проверки подлинности |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Да <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Да <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Да <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Да <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Да <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Да <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Нет <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Нет <br/> |AES/256 <br/>|RSA/112 <br/> |

Эти наборы шифров поддерживали протоколы TLS 1.0 и 1.1 до даты их амортизации. Для сред GCC High и DoD дата амортизации была 15 января 2020 г., а для сред по всему миру и GCC эта дата была 15 октября 2020 г.

| Протоколы | Имя набора шифров | Алгоритм обмена ключами/сила | Поддержка forward Secrecy | Алгоритм проверки подлинности/прочность | Cipher/Strength |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Да  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Да  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Нет  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Нет  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Нет   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Нет   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Статьи по теме

[Наборы шифров TLS в Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Шифрование в Office 365](encryption.md)
  
[Настройка шифрования в Office 365 корпоративный](set-up-encryption.md)
  
[Schannel implementation of TLS 1.0 in Windows security status update: 24 November 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Подготовка к TLS 1.2 в Office 365 и Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)