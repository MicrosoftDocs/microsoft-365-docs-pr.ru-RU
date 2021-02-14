---
title: Записи DNS для Office 365 DoD
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
description: Сводка. Записи DNS для Office 365 DoD
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693171"
---
# <a name="dns-records-for-office-365-dod"></a>Записи DNS для Office 365 DoD

*Эта статья относится к Office 365 DoD и Microsoft 365 DoD*

При подстройке к Office 365 DoD вам потребуется добавить домены SMTP и SIP в клиент Online Services.  Это можно сделать с помощью New-MsolDomain в Azure AD PowerShell или с помощью портала [Azure для](https://portal.azure.us) государственных служб, чтобы начать процесс добавления домена и доказательства его владения.

После добавления доменов в клиент и проверки воспользуйтесь следующими рекомендациями, чтобы добавить соответствующие записи DNS для служб ниже.  Возможно, потребуется изменить приведенную ниже таблицу в учете потребностей организации в отношении входящие записи MX и существующих записей автообнаружия Exchange.  Мы настоятельно рекомендуем координировать эти записи DNS с вашей командой обмена сообщениями, чтобы избежать сставок или неправильной доставки электронной почты.

## <a name="exchange-online"></a>Exchange Online

| Type (Тип) | Priority (Приоритет) | Имя узла | Указывает на адрес или значение | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (дополнительные сведения см. ниже) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 час |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Запись автообнаружия Exchange

Если вы Exchange Server локально, рекомендуем оставить существующую запись на месте во время миграции в Exchange Online и обновить ее после завершения миграции.

### <a name="exchange-online-mx-record"></a>Запись MX в Exchange Online

Значение записи MX для ваших принятых доменов следует стандартному формату, как  было отмечено выше: *tenant*.mail.protection.office365.us, заменяя клиент первой частью имени клиента по умолчанию.

Например, если имя клиента contoso.onmicrosoft.us, необходимо использовать contoso.mail.protection.office365.us  в качестве значения для записи MX.

## <a name="skype-for-business-online"></a>Skype для бизнеса Online

### <a name="cname-records"></a>Записи CNAME

| Type | Имя узла | Указывает на адрес или значение | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 час |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>Записи SRV

| Type | Служба | Протокол | Порт | Насыщенность | Priority | Имя | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1  | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 час |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1  | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Дополнительные записи DNS

> [!IMPORTANT]
> Если в зоне DNS есть существующая запись *MSOID* CNAME, ее необходимо удалить из DNS.   Запись msoid несовместима с Microsoft 365 корпоративные приложения *(ранее Office 365 профессиональныйplus)* и предотвратит успешное активацию.
