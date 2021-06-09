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

*Эта статья применяется к Office 365 и Microsoft 365 DoD*

В рамках onboarding Office 365 DoD необходимо добавить свои домены SMTP и SIP в клиента Online Services.  Это можно сделать с помощью New-MsolDomain в Azure AD PowerShell или с помощью портала правительственных служб [Azure](https://portal.azure.us) для запуска процесса добавления домена и доказывания права собственности.

После добавления доменов в клиента и проверки используйте следующие рекомендации, чтобы добавить соответствующие записи DNS для служб ниже.  Возможно, вам потребуется изменить приведенную ниже таблицу, чтобы соответствовать потребностям вашей организации в отношении входящие записи MX (s) и любой существующей записи автооткрытия Exchange(ы) у вас есть.  Мы настоятельно рекомендуем координировать эти записи DNS с вашей командой обмена сообщениями, чтобы избежать каких-либо отключений или неправильной доставки электронной почты.

## <a name="exchange-online"></a>Exchange Online

| Type (Тип) | Priority (Приоритет) | Имя узла | Адрес или значение назначения | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (см. ниже дополнительные сведения) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 час |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange Запись автооткрытия

Если вы Exchange Server, рекомендуем оставить существующую запись на месте во время миграции в Exchange Online и обновить эту запись после завершения миграции.

### <a name="exchange-online-mx-record"></a>Exchange Online Запись MX

Значение записи MX для принятых доменов следует стандартному формату, как отмечалось  выше: tenant .mail.protection.office365.us, заменив клиента первой частью имени клиента по умолчанию. 

Например, если имя клиента contoso.onmicrosoft.us, вы contoso.mail.protection.office365.us значение  для записи MX.

## <a name="skype-for-business-online"></a>Skype для бизнеса Online

### <a name="cname-records"></a>Записи CNAME

| Тип | Имя узла | Адрес или значение назначения | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 час |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>Записи SRV

| Тип | Служба | Протокол | Порт | Насыщенность | Priority | Имя | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 час |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Дополнительные записи DNS

> [!IMPORTANT]
> Если у вас есть существующая запись CNAME *msoid* в зоне DNS, необходимо удалить запись из DNS в это время.   Запись msoid несовместима с приложениями Microsoft 365 корпоративный *(ранее Office 365 профессиональный плюс)* и предотвратит успешное активацию.
