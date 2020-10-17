---
title: 'Цепочки шифрования Microsoft 365: DOD и GCC High'
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/16/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Просмотрите полный список высокодоступных корневых сертификатов DOD и GCC и центров сертификации в Microsoft 365.
ms.openlocfilehash: a933acc14f0984e4935ff6e56ccccd3aed1f16cf
ms.sourcegitcommit: 705915f8bf9b7c082d12a009523d8aa0670a74a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48493656"
---
# <a name="microsoft-365-encryption-chains---dod-and-gcc-high"></a>Цепочки шифрования Microsoft 365: DOD и GCC High

Microsoft 365 использует несколько различных поставщиков сертификатов. Ниже приведен полный список известных корневых сертификатов Microsoft 365, которые могут возникать при доступе к Microsoft 365 пользователям с помощью **DOD и GCC High** . Для получения сведений о сертификатах, которые могут потребоваться установить в собственной инфраструктуре, ознакомьтесь со статьей [Plan for СТОРОННЕГО SSL Certificates for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates).

Следующие сведения о сертификате применяются ко всем клиентам с вызовом **DOD и GCC High**.

Последнее обновление: **10/16/2020**

>[!NOTE]
>Сведения о сертификатах, применяемых к **клиентам в разных странах мира**, можно найти в [статье Microsoft 365 Encryption цепочки шифрования](encryption-office-365-certificate-chains.md).

| **Тип сертификата** | **Скачивание P7b** | **Конечные точки CRL** | **Конечные точки OCSP** |
| --- | --- | --- | --- | --- |
| Общедоступные корневые и промежуточные сертификаты | [Пакет сертификатов Microsoft 365 ITAR (P7B)](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/m365_chain_certs_itar20201012.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

Разверните корневые и промежуточные разделы ниже, чтобы просмотреть дополнительные сведения о поставщиках сертификатов.

## <a name="microsoft-365-certificate-details"></a>**Сведения о сертификате Microsoft 365**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **Subject** | CN = Балтимор Цибертруст root<br>OU = Цибертруст<br>O = Балтимор<br>C = IE |
| --- | --- |
| **Серийный номер** | 02:00:00: B9 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | 12 18:46:00 2000 время в формате UTC |
| **Срок действия не позднее** | 12 23:59:00 2025 время в формате UTC |
| **Идентификатор ключа субъекта** | в ~: 9d: 59:30:82:47:58: CC: AC:: oC: 08:54:36:86:7b: 3A: B5 |
| **Отпечаток (SHA-1)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **Отпечаток (SHA-256)** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **ПИН-код (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**ЦС облачных служб DigiCert — 1**

| **Subject** | CN = DigiCert Cloud Services CA (ЦС) — 1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert глобальный корневой ЦС<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| **Серийный номер** | 01: "9E: C6: C6: C6:3F: 59:7B: B2:0C: 33:38:/Д: 51: D8:77 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Авг 04 12:00:00 2015 UTC |
| **Срок действия не позднее** | Авг 04 12:00:00 2030 UTC |
| **Идентификатор ключа субъекта** | DD: 51: D0: a2:31:73: A9:73: AE: 8F: B4:01:7e: 5D: 8c:: 57:: 9f: F0: |
| **Идентификатор ключа центра сертификации** | него значение KeyID: 03: de: 50:35:56: D1:4c: BB: 66: F0: A3: E2:1b: 1b: C3:97: B2:3D: D1:55 |
| **Отпечаток (SHA-1)** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **Отпечаток (SHA-256)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **ПИН-код (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **URL-адреса CRL** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="digicert-cloud-services-ca-1"></a>**ЦС облачных служб DigiCert — 1**

| **Subject** | CN = DigiCert Cloud Services CA (ЦС) — 1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert глобальный корневой ЦС, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 0F: 17:1A: 48: C6: F2:23:80:92:18: CD: 2E: D6: DD: C0: E8 |
| **Длина открытого ключа** | RSA 2048 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Четверг, 24 сентября 2020 5:00 PM |
| **Срок действия не до** | Вторник, 24 сентября 2030 4:59 PM |
| **Идентификатор ключа субъекта** | DD51D0A23173A973AE8FB4017E5D8C57CB9FF0F7 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 03: de: 50:35:56: D1:4c: BB: 66: F0: A3: E2:1b: 1b: C3:97: B2:3D: D1:55 |
| **Отпечаток (SHA-1)** | B3F6B64A07BB9611F47174407841F564FB991F29 |
| **Отпечаток (SHA-256)** | 5F88694615E4C61686E106B84C3338C6720C535F60D36F61282ED15E1977DD44 |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**Глобальный корневой ЦС DigiCert**

| **Subject** | CN = DigiCert глобальный корневой ЦС<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Серийный номер** | 08:3B: E0:56:90:42:46: B1: A1:75:6A: C9:59:91: C7:4A |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | Ноя 10 00:00:00 2006 UTC |
| **Срок действия не позднее** | Ноя 10 00:00:00 2031 UTC |
| **Идентификатор ключа субъекта** | 03: de: 50:35:56: D1:4c: BB: 66: F0: A3::/1b: 1b: C3:97: B2:3D: D1:55 |
| **Идентификатор ключа центра сертификации** | него значение KeyID: 03: de: 50:35:56: D1:4c: BB: 66: F0: A3: E2:1b: 1b: C3:97: B2:3D: D1:55 |
| **Отпечаток (SHA-1)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **Отпечаток (SHA-256)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **ПИН-код (SHA-256)** | r/mIkG3eEpVdm + u/Ko/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-global-root-g2"></a>**Глобальное корневое DigiCert, G2**

| **Subject** | CN = DigiCert Global Root G2<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert Global Root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 03:3A:: F1: E6: A7:11: A9: A0: BB: 28:64: B1:1Д: 09 |
| **Длина открытого ключа** | RSA 2048 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Четверг, 1 августа 2013 5:00 AM |
| **Срок действия не до** | Пятница, 15 января 2038 4:00 AM |
| **Идентификатор ключа субъекта** | 4E2254201895E6E36EE60FFAFAB912ED06178F39 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 4E: 22:54:20:18:95: E6: E3:6e: E6:0F: FA: FA: B9:12: Ed: 06:17:8F: 39 |
| **Отпечаток (SHA-1)** | DF3C24F9BFD666761B268073FE06D1CC8D4F82A4 |
| **Отпечаток (SHA-256)** | CB3CCBB76031E5E0138F8DD39A23F9DE47FFC35E43C1144CEA27D46A5AB1CB5F |

### <a name="digicert-high-assurance-ev-root-ca"></a>**Корневой центр сертификации высокой надежности DigiCert**

| **Subject** | CN = DigiCert (корневой центр сертификации высокой надежности)<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Серийный номер** | 02: AC: 5C: 26:6A: 0B: 40:9B: 8F: 0B: 79: F2: AE: 46:25:77 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | Ноя 10 00:00:00 2006 UTC |
| **Срок действия не позднее** | Ноя 10 00:00:00 2031 UTC |
| **Идентификатор ключа субъекта** | B1:3E: C3:69:03: в: БФ: 47:01:: 98:26:: 08:02: |
| **Идентификатор ключа центра сертификации** | него значение KeyID: B1:3E: C3:69:03: в: БФ: 47:01: D4:98:26: стр: 08:02::: C3 |
| **Отпечаток (SHA-1)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **Отпечаток (SHA-256)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **ПИН-код (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**DigiCert SHA2 расширенный ЦС сервера проверки подлинности**

| **Subject** | CN = DigiCert SHA2 расширенный ЦС сервера проверки подлинности<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Серийный номер** | 0C: 79: A9:44: B0:8C: 11:95:20:92:61:5F: E2:6B: 1Д: 83 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Oct 22 00:00:00 2013 UTC |
| **Срок действия не позднее** | Oct 22 00:00:00 2028 UTC |
| **Идентификатор ключа субъекта** | ОБЪЕМНАЯ: D3:50: A5: D6: A0: AD: EE: 3:4A: 60:0A: 65: D3:21:: 0F |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: B1:3E: C3:69:03: в: БФ: 47:01: D4:98:26: стр: 08:02::: C3 |
| **Отпечаток (SHA-1)** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **Отпечаток (SHA-256)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="digicert-sha2-secure-server-ca"></a>**DigiCert SHA2 безопасности ЦС сервера**

| **Subject** | CN = DigiCert SHA2 Secure CA Server<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert глобальный корневой ЦС, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 01: ДЕМО: A3: A3:6E: CA: 75: C8:88:43:8B: 72:4B: CF: BC: 91 |
| **Длина открытого ключа** | RSA 2048 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Пятница, 8 марта 2013 4:00 AM |
| **Срок действия не до** | Среда, 8 марта 2023 4:00 AM |
| **Идентификатор ключа субъекта** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 03: de: 50:35:56: D1:4c: BB: 66: F0: A3: E2:1b: 1b: C3:97: B2:3D: D1:55 |
| **Отпечаток (SHA-1)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **Отпечаток (SHA-256)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**DigiCert SHA2 безопасности ЦС сервера**

| **Subject** | CN = DigiCert SHA2 Secure CA Server<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert глобальный корневой ЦС, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 02:74:2E: AA: 17: CA: 8E: 21: C7:17: BB: 1F: FC: ДЕМОН: 0C: A0 |
| **Длина открытого ключа** | RSA 2048 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Вторник, 22 сентября 2020 5:00 PM |
| **Срок действия не до** | Воскресенье, 22 сентября 2030 4:59 PM |
| **Идентификатор ключа субъекта** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 03: de: 50:35:56: D1:4c: BB: 66: F0: A3: E2:1b: 1b: C3:97: B2:3D: D1:55 |
| **Отпечаток (SHA-1)** | 626D44E704D1CEABE3BF0D53397464AC8080142C |
| **Отпечаток (SHA-256)** | C1AD7778796D20BCA65C889A2655021156528BB62FF5FA43E1B8E5A83E3D2EAA |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="digicert-tls-rsa-sha256-2020-ca1"></a>**DigiCert TLS RSA SHA256 2020 CA1**

| **Subject** | CN = DigiCert TLS RSA SHA256 2020 CA1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert глобальный корневой ЦС, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 0A: 35:08: D5:5C: 29:2B: 01:7D: F8: AD: 65: C0:0F: F7: E4 |
| **Длина открытого ключа** | RSA 2048 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Среда, 23 сентября 2020 5:00 PM |
| **Срок действия не до** | Понедельник, 23 сентября 2030 4:59 PM |
| **Идентификатор ключа субъекта** | B76BA2EAA8AA848C79EAB4DA0F98B2C59576B9F4 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 03: de: 50:35:56: D1:4c: BB: 66: F0: A3: E2:1b: 1b: C3:97: B2:3D: D1:55 |
| **Отпечаток (SHA-1)** | 6938FD4D98BAB03FAADB97B34396831E3780AEA1 |
| **Отпечаток (SHA-256)** | 25768713D3B459F9382D2A594F85F34709FD2A8930731542A4146FFB246BEC69 |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="entrust-root-certification-authority"></a>**Корневой центр сертификации ентруст**

| **Subject** | CN = Ентруст корневой центр сертификации<br>OU = "(c) 2006 Ентруст, Inc."<br>OU = www. ентруст. NET/CPS включен по ссылке<br>OU = см www.entrust.net/legal-terms<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| --- | --- |
| **Серийный номер** | 45:6B: 50:54 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | Ноя 27 12:23:42 2006 UTC |
| **Срок действия не позднее** | Ноя 27 12:53:42 2026 UTC |
| **Идентификатор ключа субъекта** | 68:90:1: 67: A4: A4: A4:53:: 86:86:66: A4: F1:: 4B: 43: ФБ: 84:: 6D |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 68:90:1: 67: A4: A4:53:: A4:: 86:66:66: A4: F1:: 4b: 43: ФБ: 84:6d |
| **Отпечаток (SHA-1)** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **Отпечаток (SHA-256)** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Корневой центр сертификации ентруст — G2**

| **Subject** | CN = Ентруст корневой центр сертификации — G2<br>OU = &quot; (c) 2009 ентруст, Inc. — только для уполномоченного использования&quot;<br>OU = см www.entrust.net/legal-terms<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| --- | --- |
| **Серийный номер** | 4A: 53:8C: 28 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | 07 17:25:54 2009 июля (UTC) |
| **Срок действия не позднее** | Dec 07 17:55:54 2030 UTC |
| **Идентификатор ключа субъекта** | 6a: 72:26:7A: D0:1e: EF: 7D: E7:3b: 69:51: D4:6c: 8D: 9f: 90:12:66: AB |
| **Отпечаток (SHA-1)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **Отпечаток (SHA-256)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **ПИН-код (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Центр сертификации Entrust.net (2048)**

| **Subject** | CN = Ентруст. NET центр сертификации (2048)<br>OU = (c) 1999 Entrust.net с ограничениями<br>OU = www. ентруст. NET/CPS \_ 2048. по ссылке ref. (Limit s лиаб.)<br>O = Ентруст. NET |
| --- | --- |
| **Серийный номер** | 38:63: DE: F8 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | Dec 24 17:50:51 1999 UTC |
| **Срок действия не позднее** | 24 14:15:12 2029 июля (UTC) |
| **Идентификатор ключа субъекта** | 55: E4:81: D1:11:80:: D8:89: B9:08: A3:: 9:: a1:24:09:16: B9:70 |
| **Отпечаток (SHA-1)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **Отпечаток (SHA-256)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **ПИН-код (SHA-256)** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Центр сертификации ентруст — L1C**

| **Subject** | CN = центр сертификации Ентруст — L1C<br>OU = &quot; (c) 2009 ентруст, Inc.&quot;<br>OU = www. ентруст. NET/РПА внедряется по ссылке<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| --- | --- |
| **Издатель** | CN = Ентруст. NET центр сертификации (2048)<br>OU = (c) 1999 Entrust.net с ограничениями<br>OU = www. ентруст. NET/CPS \_ 2048. по ссылке ref. (Limits лиаб.)<br>O = Ентруст. NET |
| **Серийный номер** | 4C: 0E: 8C: 39 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | Ноя 11 15:40:40 2011 UTC |
| **Срок действия не позднее** | Ноя 11 02:51:17 2021 UTC |
| **Идентификатор ключа субъекта** | 1E: F1: AB: 89:89:06: F8:49:0F: 01:33:77:7A: 7c: 93:28:4D |
| **Идентификатор ключа центра сертификации** | него значение KeyID: 55: E4:81: D1:11:80:: D8:89: B9:08: A3:23:: a1: мм: 09:16: B9:70 |
| **Отпечаток (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Отпечаток (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **ПИН-код (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **URL-адреса CRL** | http://crl.entrust.net/2048ca.crl |
| **URL-адреса OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Центр сертификации ентруст — L1E**

| **Subject** | CN = центр сертификации Ентруст — L1E<br>OU = &quot; (c) 2009 ентруст, Inc.&quot;<br>OU = www. ентруст. NET/РПА внедряется по ссылке<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| --- | --- |
| **Издатель** | CN = Ентруст. NET центр сертификации (2048)<br>OU = (c) 1999 Entrust.net с ограничениями<br>OU = www. ентруст. NET/CPS \_ 2048. по ссылке ref. (Limits лиаб.)<br>O = Ентруст. NET |
| **Серийный номер** | 4C: 0E: C9:18 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha1RSA |
| **Срок действия не ранее** | Ноя 11 15:40:40 2011 UTC |
| **Срок действия не позднее** | Ноя 11 02:51:17 2021 UTC |
| **Идентификатор ключа субъекта** | 5B: 41:41:8A: B2: C4: ": C4:: 43: БФ: C8:54:41:55:9D:: A1: |
| **Идентификатор ключа центра сертификации** | него значение KeyID: 68:90:1: 67: A4: A4:53:: A4:: 86:66:66: A4: F1:: 4b: 43: ФБ: 84:6d |
| **Отпечаток (SHA-1)** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **Отпечаток (SHA-256)** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **URL-адреса CRL** | http://crl.entrust.net/rootca1.crl |
| **URL-адреса OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Центр сертификации ентруст — L1K**

| **Subject** | CN = центр сертификации Ентруст — L1K<br>OU = &quot; (c) 2012 ентруст, Inc. — только для уполномоченного использования&quot;<br>OU = см www.entrust.net/legal-terms<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| --- | --- |
| **Издатель** | CN = Ентруст корневой центр сертификации — G2<br>OU = &quot; (c) 2009 ентруст, Inc. — только для уполномоченного использования&quot;<br>OU = см www.entrust.net/legal-terms<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| **Серийный номер** | 0E: E9:4C: С3:00:00:00:00:51:: 77:85 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Oct 05 19:13:56 2015 UTC |
| **Срок действия не позднее** | Dec 05 19:43:56 2030 UTC |
| **Идентификатор ключа субъекта** | 82: a2:70:74: DD:: BC: 53:3F: CF: 7b: D4:: CD: 7F:: 60: C6:0a: 4c: БФ |
| **Идентификатор ключа центра сертификации** | него значение KeyID: 6a: 72:25:7A: D0:1e: EF: 7D: E7:3b: 69:51: D4:6c: 8D: 9f: 90:12:66: AB |
| **Отпечаток (SHA-1)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **Отпечаток (SHA-256)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **ПИН-код (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **URL-адреса CRL** | http://crl.entrust.net/g2ca.crl |
| **URL-адреса OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Центр сертификации ентруст — L1M**

| **Subject** | CN = Ентруст центр сертификации — L1M, OU = &quot; (c) 2014 ентруст, Inc. — только для авторизованного использования&quot;<br>OU = см www.entrust.net/legal-terms<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| --- | --- |
| **Издатель** | CN = Ентруст корневой центр сертификации — G2<br>OU = &quot; (c) 2009 ентруст, Inc. — только для уполномоченного использования&quot;<br>OU = см www.entrust.net/legal-terms<br>O = &quot; ентруст, Inc.&quot;<br>C = US |
| **Серийный номер** | 61: A1: E7: D2:00:00:00:00:51: D3:66: A6 |
| **Длина открытого ключа** | RSA 2048 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Dec 15 07:25:03 2014 UTC |
| **Срок действия не позднее** | Oct 15 08:55:03 2030 UTC |
| **Идентификатор ключа субъекта** | C3: F7: D0: B5:2A: 30: AD: AF: 0D: 91:21:70:39:54: ДД: BC: 89:54: C7:3A |
| **Идентификатор ключа центра сертификации** | него значение KeyID: 6a: 72:25:7A: D0:1e: EF: 7D: E7:3b: 69:51: D4:6c: 8D: 9f: 90:12:66: AB |
| **Отпечаток (SHA-1)** | CC136695639065FAB47074D28C55314C66077E90 |
| **Отпечаток (SHA-256)** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **URL-адреса CRL** | http://crl.entrust.net/g2ca.crl |
| **URL-адреса OCSP** | http://ocsp.entrust.net |

### <a name="microsoft-azure-tls-issuing-ca-01"></a>**Центр сертификации Microsoft Azure TLS 01**

| **Subject** | CN = Microsoft Azure TLS выдача ЦС 01<br>O = Корпорация Майкрософт<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert Global Root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 0A: AF: A6: C5: CA: 63: C4:51:41::: 3B: E1: F7: C7:17 |
| **Длина открытого ключа** | RSA 4096 бит |
| **Алгоритм подписи** | sha384RSA |
| **Срок действия не ранее** | Среда, 29 июля, 2020 5:30 AM |
| **Срок действия не до** | Четверг, 27 июня, 2024 4:59 PM |
| **Идентификатор ключа субъекта** | 0F205DD7A15795DB92CF2BD0C7C27704CE728076 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 4E: 22:54:20:18:95: E6: E3:6e: E6:0F: FA: FA: B9:12: Ed: 06:17:8F: 39 |
| **Отпечаток (SHA-1)** | 2F2877C5D778C31E0F29C7E371DF5471BD673173 |
| **Отпечаток (SHA-256)** | 24C7299864E0A2A6964F551C0E8DF2461532FA8C48E4DBBB6080716691F190E5 |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-02"></a>**Выставляющий ЦС Microsoft Azure TLS 02**

| **Subject** | CN = Microsoft Azure TLS, выставляющий ЦС 02<br>O = Корпорация Майкрософт<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert Global Root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 0C: 6A: E9:7C: CE: D5:99:83:86:90: A0:0A: 9E:: 32:14 |
| **Длина открытого ключа** | RSA 4096 бит |
| **Алгоритм подписи** | sha384RSA |
| **Срок действия не ранее** | Среда, 29 июля, 2020 5:30 AM |
| **Срок действия не до** | Четверг, 27 июня, 2024 4:59 PM |
| **Идентификатор ключа субъекта** | 00AB91FC216226979AA8791B61419060A96267FD |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 4E: 22:54:20:18:95: E6: E3:6e: E6:0F: FA: FA: B9:12: Ed: 06:17:8F: 39 |
| **Отпечаток (SHA-1)** | E7EEA674CA718E3BEFD90858E09F8372AD0AE2AA |
| **Отпечаток (SHA-256)** | 15A98761EBE011554DA3A46D206B0812CB2EB69AE87AAA11A6DD4CB84ED5142A |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-05"></a>**ЦС Microsoft Azure TLS, выставляющий 05**

| **Subject** | CN = Microsoft Azure TLS выдачи ЦС 05<br>O = Корпорация Майкрософт<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert Global Root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 0D: 7B: ED: E9:7D: 82:09:96:7A: 52:63:1B: 8B: ДД: 18: BD |
| **Длина открытого ключа** | RSA 4096 бит |
| **Алгоритм подписи** | sha384RSA |
| **Срок действия не ранее** | Среда, 29 июля, 2020 5:30 AM |
| **Срок действия не до** | Четверг, 27 июня, 2024 4:59 PM |
| **Идентификатор ключа субъекта** | C7B29C7F1CE3B85AEFE9681AA85D94C126526A68 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 4E: 22:54:20:18:95: E6: E3:6e: E6:0F: FA: FA: B9:12: Ed: 06:17:8F: 39 |
| **Отпечаток (SHA-1)** | 6C3AF02E7F269AA73AFD0EFF2A88A4A1F04ED1E5 |
| **Отпечаток (SHA-256)** | D6831BA43607F5AC19778D627531562AF55145F191CAB5EFAFA0E0005442B302 |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-06"></a>**Центр сертификации Microsoft Azure TLS 06**

| **Subject** | CN = Microsoft Azure TLS выдача ЦС 06<br>O = Корпорация Майкрософт<br>C = US |
| --- | --- |
| **Издатель** | CN = DigiCert Global Root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Серийный номер** | 02: E7:91:71: ФБ: 80:21: E9:3F: E2: D9:83:83:4C: 50: C0 |
| **Длина открытого ключа** | RSA 4096 бит |
| **Алгоритм подписи** | sha384RSA |
| **Срок действия не ранее** | Среда, 29 июля, 2020 5:30 AM |
| **Срок действия не до** | Четверг, 27 июня, 2024 4:59 PM |
| **Идентификатор ключа субъекта** | D5C1673AC2A39DF477525B59123829E65568BBA5 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: 4E: 22:54:20:18:95: E6: E3:6e: E6:0F: FA: FA: B9:12: Ed: 06:17:8F: 39 |
| **Отпечаток (SHA-1)** | 30E01761AB97E59A06B41EF20AF6F2DE7EF4F7B0 |
| **Отпечаток (SHA-256)** | 48FF8B494668C752304B48BFE818758987DEF6582E5F09B921F4B60BB3D6A8DD |
| **URL-адреса CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-1"></a>**ЦС 1 Microsoft IT TLS**

| **Subject** | CN = ЦС Microsoft IT TLS 1<br>OU = Microsoft IT<br>O = Корпорация Майкрософт<br>L = Redmond<br>S = Вашингтон<br>C = US |
| --- | --- |
| **Издатель** | CN = Балтимор Цибертруст root<br>OU = Цибертруст<br>O = Балтимор<br>C = IE |
| **Серийный номер** | 08: B8:7A: 50:1B:: 9C: DA: 2D: 16:4D: 3E: 39:51: БФ: 55 |
| **Длина открытого ключа** | RSA 4096 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | 20 12:51:28 2016 время в формате UTC |
| **Срок действия не позднее** | 20 12:51:28 2024 время в формате UTC |
| **Идентификатор ключа субъекта** | 58:88:9f: D6: контроллер домена: 9C: 48:22: B7:14:356: FF: 84:88: E8: E6:85: FF: FA: 7D |
| **Идентификатор ключа центра сертификации** | него значение KeyID: напряжение на: 9d: 59:30:82:47:58: CC: AC: FA: 08:54:36:86:7b: 3A: B5:04:4d: F0 |
| **Отпечаток (SHA-1)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **Отпечаток (SHA-256)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **ПИН-код (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + J3 + b2LiybIw = |
| **URL-адреса CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**ЦС 2 Microsoft IT TLS 2**

| **Subject** | CN = ЦС Microsoft IT TLS 2<br>OU = Microsoft IT<br>O = Корпорация Майкрософт<br>L = Redmond<br>S = Вашингтон<br>C = US |
| --- | --- |
| **Издатель** | CN = Балтимор Цибертруст root<br>OU = Цибертруст<br>O = Балтимор<br>C = IE |
| **Серийный номер** | 0F: 2C: 10: C9:5B: 06: C0:93:7F: B8: D4:49. |
| **Длина открытого ключа** | RSA 4096 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | 20 12:51:57 2016 время в формате UTC |
| **Срок действия не позднее** | 20 12:51:57 2024 время в формате UTC |
| **Идентификатор ключа субъекта** | 91:9E: 3b: 44:6c: 3D: 57:9C:: 77:2A: 34: D7:4F: D1: CC: 4A: 97:2c: Da |
| **Идентификатор ключа центра сертификации** | него значение KeyID: напряжение на: 9d: 59:30:82:47:58: CC: AC: FA: 08:54:36:86:7b: 3A: B5:04:4d: F0 |
| **Отпечаток (SHA-1)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **Отпечаток (SHA-256)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **ПИН-код (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **URL-адреса CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**ЦС Microsoft IT TLS 4**

| **Subject** | CN = ЦС Microsoft IT TLS 4<br>OU = Microsoft IT<br>O = Корпорация Майкрософт<br>L = Redmond<br>S = Вашингтон<br>C = US |
| --- | --- |
| **Издатель** | CN = Балтимор Цибертруст root<br>OU = Цибертруст<br>O = Балтимор<br>C = IE |
| **Серийный номер** | 0B: В: B3: B3: B0:3E: B1: A9: F6: C4:60:92:6A: A8: CD: FE: B3 |
| **Длина открытого ключа** | RSA 4096 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | 20 12:52:38 2016 время в формате UTC |
| **Срок действия не позднее** | 20 12:52:38 2024 время в формате UTC |
| **Идентификатор ключа субъекта** | 7A: 7b: 8c: C1: CF: E7: a0: CA: 1C: D4:6b: FA: ФБ: E1::: |
| **Идентификатор ключа центра сертификации** | него значение KeyID: напряжение на: 9d: 59:30:82:47:58: CC: AC: FA: 08:54:36:86:7b: 3A: B5:04:4d: F0 |
| **Отпечаток (SHA-1)** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **Отпечаток (SHA-256)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **ПИН-код (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/ки + + mV7FgIcbn4WhMz1I2k = |
| **URL-адреса CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**ЦС Microsoft IT TLS 5**

| **Subject** | CN = ЦС Microsoft IT TLS 5<br>OU = Microsoft IT<br>O = Корпорация Майкрософт<br>L = Redmond<br>S = Вашингтон<br>C = US |
| --- | --- |
| **Издатель** | CN = Балтимор Цибертруст root<br>OU = Цибертруст<br>O = Балтимор<br>C = IE |
| **Серийный номер** | 08:88:88: CD: 52:5F: 19:24:44:4D: 14: A5:82:91: ДЕ: B9:52 |
| **Длина открытого ключа** | RSA 4096 бит (e 65537) |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | 20 12:53:03 2016 время в формате UTC |
| **Срок действия не позднее** | 20 12:53:03 2024 время в формате UTC |
| **Идентификатор ключа субъекта** | 08: FE: 25:9f: 74:: 87:87:04: C2: BC: BB: 8E: A8:38:5f: 33: C6: D1:6c: 65 |
| **Идентификатор ключа центра сертификации** | него значение KeyID: напряжение на: 9d: 59:30:82:47:58: CC: AC: FA: 08:54:36:86:7b: 3A: B5:04:4d: F0 |
| **Отпечаток (SHA-1)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **Отпечаток (SHA-256)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **ПИН-код (SHA-256)** | Ркбкб + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **URL-адреса CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-01"></a>**ЦС Microsoft RSA TLS 01**

| **Subject** | CN = Microsoft RSA TLS ЦС 01<br>O = Корпорация Майкрософт<br>C = US |
| --- | --- |
| **Издатель** | CN = Балтимор Цибертруст root, OU = Цибертруст, O = Балтимор, C = IE |
| **Серийный номер** | 0F: 14:96:5F: 20:20:69:99:4F: D5: C7: AC: 78:89:41: E2 |
| **Длина открытого ключа** | RSA 4096 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Вторник 21 июля, 2020 4:00 PM |
| **Срок действия не до** | Вторник, 8 октября 2024 12:00 AM |
| **Идентификатор ключа субъекта** | B5760C3011CEC792424D4CC75C2CC8A90CE80B64 |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: напряжение на: 9d: 59:30:82:47:58: CC: AC: FA: 08:54:36:86:7b: 3A: B5:04:4d: F0 |
| **Отпечаток (SHA-1)** | 703D7A8F0EBF55AAA59F98EAF4A206004EB2516A |
| **Отпечаток (SHA-256)** | 04EEEA8E50B4775B3C24797262917EE50002EC4C75B56CDF3EE1C18CFCA5BA52 |
| **URL-адреса CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-02"></a>**ЦС Microsoft RSA TLS 02**

| **Subject** | CN = Microsoft RSA TLS ЦС 02<br>O = Корпорация Майкрософт<br>C = US |
| --- | --- |
| **Издатель** | CN = Балтимор Цибертруст root, OU = Цибертруст, O = Балтимор, C = IE |
| **Серийный номер** | 0F: A7:47:22: C5:3D: 88: C8:0F: 58:9E: ФБ: 1F: 9D: 4A: 3A |
| **Длина открытого ключа** | RSA 4096 бит |
| **Алгоритм подписи** | sha256RSA |
| **Срок действия не ранее** | Вторник 21 июля, 2020 4:00 PM |
| **Срок действия не до** | Вторник, 8 октября 2024 12:00 AM |
| **Идентификатор ключа субъекта** | FF2F7FE106F438F32DED258D98C2FE0EF66CFCFA |
| **Идентификатор ключа центра сертификации** | Него значение KeyID: напряжение на: 9d: 59:30:82:47:58: CC: AC: FA: 08:54:36:86:7b: 3A: B5:04:4d: F0 |
| **Отпечаток (SHA-1)** | B0C2D2D13CDD56CDAA6AB6E2C04440BE4A429C75 |
| **Отпечаток (SHA-256)** | 05E4005DB0C382F3BD66B47729E9011577601BF6F7B287E9A52CED710D258346 |
| **URL-адреса CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URL-адреса OCSP** | http://ocsp.digicert.com |
