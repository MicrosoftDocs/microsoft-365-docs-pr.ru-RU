---
title: Записи DNS для Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Сводка: записи DNS для Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693160"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Записи DNS для Office 365 GCC High

*Эта статья относится к пакету Office 365 GCC High и Microsoft 365 GCC High*

В процессе входящей миграции в Office 365 GCC High необходимо добавить домены SMTP и SIP в клиент Интернет-служб.  Это можно сделать с помощью командлета New – Мсолдомаин в Azure AD PowerShell или на [портале для государственных учреждений Azure](https://portal.azure.us) , чтобы начать процесс добавления домена и подтверждения владения.

После добавления доменов к клиенту и проверки подлинности добавьте соответствующие записи DNS для служб ниже, следуя приведенным ниже рекомендациям.  Возможно, вам потребуется изменить приведенную ниже таблицу в соответствии с потребностями Организации относительно входящих записей MX и всех имеющихся записей автообнаружения Exchange.  Мы настоятельно рекомендуем координировать эти записи DNS с помощью команды обмена сообщениями, чтобы избежать каких-либо непростостей или неправильной доставки электронной почты.

## <a name="exchange-online"></a>Exchange Online

| Type (Тип) | Priority (Приоритет) | Имя узла | Указывает на адрес или значение | TTL |
| --- | --- | --- | --- | --- |
| MX | нуль | @ | *клиент*. mail.Protection.Office365.US (Дополнительные сведения см. ниже) | 1 Hour |
| TXT | - | @ | v = spf1 включение:SPF. Protection. Office365. US — ALL | 1 час |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Запись автообнаружения Exchange

При наличии локального сервера Exchange Server мы рекомендуем оставить существующую запись на месте во время миграции в Exchange Online и обновить эту запись после завершения миграции. 

### <a name="exchange-online-mx-record"></a>Запись MX Exchange Online

Значение записи MX для обслуживаемых доменов соответствует стандартному формату, как указано выше: *клиент*. mail.Protection.Office365.US, заменяя *клиент* первой частью имени клиента по умолчанию.

Например, если имя клиента — contoso.onmicrosoft.us, вы бы использовали **contoso.mail.Protection.Office365.US** в качестве значения для записи MX.

## <a name="skype-for-business-online"></a>Skype для бизнеса Online

### <a name="cname-records"></a>Записи CNAME

| Тип | Имя узла | Указывает на адрес или значение | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 час |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 Hour |

### <a name="srv-records"></a>Записи SRV

| Тип | Служба | Протокол | Порт | Насыщенность | Priority | Имя | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_аутентифицирован | 443 | 1,1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 час |
| SRV | \_сипфедератионтлс | \_семейства | 5061 | 1,1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Дополнительные записи DNS

> [!IMPORTANT]
> Если у вас есть запись CNAME *msoID* в зоне DNS, в настоящее время необходимо **Удалить** эту запись из DNS.  Запись msoID несовместима с Microsoft 365 Enterprise Apps *(прежнее название — Office 365 профессиональный плюс)* и не позволит выполнить активацию.
