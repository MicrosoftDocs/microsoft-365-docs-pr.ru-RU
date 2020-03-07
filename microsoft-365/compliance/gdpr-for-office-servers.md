---
title: GDPR для серверов Office
description: Узнайте, как обеспечивать соблюдение требований GDPR на локальных серверах Office.
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
ms.openlocfilehash: b50722d7f37b54b38bac259b7c42d3bd782dfb3d
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557959"
---
# <a name="gdpr-for-office-on-premises-servers"></a>GDPR для локальных серверов Office

Общий регламент по защите данных (GDPR) устанавливает требования в отношении защиты персональных данных и надлежащего реагирования на запросы субъектов данных. В этой серии статей представлены рекомендуемые подходы для локальных рабочих нагрузок.

-   [SharePoint Server](gdpr-for-sharepoint-server.md)

-   [Exchange Server](gdpr-for-exchange-server.md)

-   [Skype для бизнеса Server](gdpr-for-skype-for-business-server.md)

-   [Project Server](gdpr-for-project-server.md)

-   [Сервер Office Web Apps и Office Online Server](gdpr-for-office-online-server.md)

-   [Локальные общие папки](gdpr-for-on-premises-file-shares.md)

Дополнительные сведения о GDPR и поддержке, которую может оказать вам корпорация Майкрософт см. в [центре управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).

Прежде чем выполнять какие-либо действия с локальными данными, проконсультируйтесь с вашими юристами и группой по обеспечению соответствия требованиям, чтобы получить рекомендации и сведения о существующих схемах классификации и подходах к работе с персональными данными. Рекомендации по разработке и расширению схем классификации корпорации Майкрософт представлены в наборе средств для обнаружения данных GDPR по адресу [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). В этом наборе средств также описываются способы перемещения локальных данных в облако, где можно использовать более сложные функции для управления данными. В статьях из этого раздела представлены рекомендации по работе с данными, которые должны оставаться в локальной среде.

Ниже перечислены рекомендуемые функции для обнаружения, классификации, защиты и мониторинга персональные данных для каждой из этих рабочих нагрузок. Дополнительные сведения см. в статьях этого раздела.

![](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a>Описание иллюстрации

Для работы специальных возможностей примеры на рисунке также приведены в таблице ниже.

|             |Общие папки Windows Server|SharePoint Server|Exchange Server|Skype для бизнеса|Project Server|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|Обнаружение|Сканер Azure Information Protection*|Центр поиска или обнаружение электронных данных (после классификации данных); сканер Azure Information Protection*|Портал обнаружения электронных данных Exchange|Портал обнаружения электронных данных Exchange|Скрипты SQL для обнаружения и экспорта|
|Классификация|Сканер Azure Information Protection*; типы конфиденциальной информации Office 365|Сканер Azure Information Protection*; типы конфиденциальной информации Office 365|Теги и политики хранения Exchange|Теги и политики хранения Exchange||
|Защита||Правила защиты от потери данных Exchange Server; разрешения, защита IRM для библиотек|Правила защиты от потери данных Exchange Server; интеграция IRM с Exchange Server|||
|Мониторинг|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|Интеграция журналов с инструментами SIEM|

* Обратите внимание, что система защиты шифрует файл. Соответственно, сервер SharePoint не может найти конфиденциальную информацию в защищенных файлах.
