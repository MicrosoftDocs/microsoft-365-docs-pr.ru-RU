---
title: GDPR для серверов Office
description: Узнайте, как обеспечить соблюдение требований Общего регламента по защите данных (GDPR) на локальных серверах Office.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547335"
---
# <a name="gdpr-for-office-on-premises-servers"></a>GDPR для локальных серверов Office

Общий регламент по защите данных (GDPR) устанавливает требования в отношении защиты персональных данных и надлежащего реагирования на запросы субъектов данных. В этой серии статей представлены рекомендуемые подходы для локальных рабочих нагрузок.

- [SharePoint Server](gdpr-for-sharepoint-server.md)

- [Exchange Server](gdpr-for-exchange-server.md)

- [Skype для бизнеса Server](gdpr-for-skype-for-business-server.md)

- [Project Server](gdpr-for-project-server.md)

- [Сервер Office Web Apps и Office Online Server](gdpr-for-office-online-server.md)

- [Локальные общие папки](gdpr-for-on-premises-file-shares.md)

Дополнительные сведения о GDPR и поддержке, которую может оказать вам корпорация Майкрософт см. в [центре управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).

Прежде чем выполнять какие-либо действия с локальными данными, проконсультируйтесь с вашими юристами и группой по обеспечению соответствия требованиям, чтобы получить рекомендации и сведения о существующих схемах классификации и подходах к работе с персональными данными. Рекомендации по разработке и расширению схем классификации корпорации Майкрософт представлены в наборе средств для обнаружения данных GDPR по адресу [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). В этом наборе средств также описываются способы перемещения локальных данных в облако, где можно использовать более сложные функции для управления данными. В статьях из этого раздела представлены рекомендации по работе с данными, которые должны оставаться в локальной среде.

Ниже перечислены рекомендуемые функции для обнаружения, классификации, защиты и мониторинга персональные данных для каждой из этих рабочих нагрузок. Дополнительные сведения см. в статьях этого раздела.

![Схема с описанием возможностей обнаружения, классификации, защиты и отслеживания персональных данных для рабочих нагрузок](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a>Описание иллюстрации

Для работы специальных возможностей примеры на рисунке также приведены в таблице ниже.

****

|Действие|Общие папки Windows Server|SharePoint Server|Exchange Server|Skype для бизнеса|Project Server|
|---|---|---|---|---|---|
|Поиск|Сканер Azure Information Protection<sup>\*</sup>|Центр поиска или обнаружение электронных данных (после классификации данных) <br/><br/> Сканер Azure Information Protection<sup>\*</sup>|Портал обнаружения электронных данных Exchange|Портал обнаружения электронных данных Exchange|Скрипты SQL для обнаружения и экспорта|
|Классификация|Сканер Azure Information Protection<sup>\*</sup> <br/><br/> Типы конфиденциальной информации Office 365|Сканер Azure Information Protection<sup>\*</sup> <br/><br/> Типы конфиденциальной информации Office 365|Теги и политики хранения Exchange|Теги и политики хранения Exchange||
|Защитить||Правила защиты от потери данных Exchange Server <br/><br/> Разрешения, защита IRM для библиотек|Правила защиты от потери данных Exchange Server <br/><br/> Интеграция IRM с Exchange Server|||
|Отслеживать|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|
|

<sup>\*</sup> Обратите внимание, что система защиты шифрует файл. Соответственно, SharePoint Server не может найти типы конфиденциальной информации в защищенных файлах.
