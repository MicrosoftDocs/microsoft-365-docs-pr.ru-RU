---
title: Варианты соответствия требованиям для групп Microsoft 365, групп и совместной работы SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Узнайте о вариантах соответствия требованиям для групп Microsoft 365, Teams и SharePoint для совместной работы.
ms.openlocfilehash: cc8f7391b03cc65ba66cca6cf010137e3843ab05
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662793"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Варианты соответствия требованиям для групп Microsoft 365, групп и совместной работы SharePoint

Microsoft 365 предлагает полный набор средств для обеспечения соответствия требованиям пользователей в Организации. Изучите эти параметры и определите, как они соответствуют потребностям вашей компании, чувствительность данных и область сотрудников, с которыми ваши пользователи должны работать совместно.

В следующей таблице представлены краткие сведения о средствах контроля соответствия требованиям, доступных в Microsoft 365. Дополнительные сведения приведены в следующих разделах.

|Категория|Описание|Справочные материалы|
|:-------|:----------|:--------|
|Хранение данных|||
||Сохранение групп почты и контента SharePoint|[Узнайте о политиках хранения для SharePoint и OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Сохранение чата и сообщений|[Узнайте о политиках хранения для Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Классификация сведений|||
||Классификация групп и Teams|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Автоматическая классификация конфиденциального содержимого|[Автоматическое применение метки конфиденциальности к содержимому](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Шифрование конфиденциального содержимого|[Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Защита информации|||
||Предотвращение потери конфиденциальной информации|[Общие сведения о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Защита конфиденциальной информации в чате.|[Защита от потери данных и Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Определение конфиденциальной информации Организации|[Пользовательские типы конфиденциальной информации](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Сегментация пользователей|||
||Ограничение обмена данными между сегментами пользователей|[Информационные барьеры](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Хранение данных

Политики хранения доступны для хранения или удаления элементов, используемых для совместной работы в группах и командах, в том числе файлов, сообщений и сообщений электронной почты. Политики можно настроить для сохранения и удаления, для сохранения только или для удаления. Сведения, покрываемые политикой хранения, защищены в случае истечения срока действия группы или группы или их удаления.

Настройка политики хранения для групп Microsoft 365 охватывает почтовые ящики групп и связанные с ними сайты и файлы SharePoint.

- [Узнайте о политиках хранения для SharePoint и OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Политики хранения для Teams сохраняют сообщения в чате и каналах. Сообщения в чате и каналах хранятся в почтовых ящиках Exchange, но не затрагиваются политиками хранения Exchange. Необходимо настроить политики хранения для применения к обсуждениям Teams и сообщениям канала teams:

- [Узнайте о политиках хранения для Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Политики хранения в Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Можно настроить одну политику хранения для применения к группам Microsoft 365, чат и сообщениям канала Teams. 

Дополнительные ресурсы:

- [Сведения о политиках хранения](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Теги хранения и политики хранения](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) в Exchange

## <a name="information-classification"></a>Классификация сведений

Метки чувствительности можно использовать для управления гостевым доступом, обеспечения конфиденциальности групп и групп, а также для доступа к неуправляемым устройствам для групп и Teams. При применении метки эти параметры автоматически настраиваются, как указано в параметрах метки.

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Вы можете настроить Microsoft 365 для автоматического применения меток конфиденциальности к файлам и сообщениям электронной почты на основе заданных вами критериев, включая обнаружение типов конфиденциальной информации или совпадение с шаблонами с помощью классификаторов, которые можно использовать для обучения.

- [Автоматическое применение метки конфиденциальности к содержимому](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Метки чувствительности можно использовать для шифрования файлов, разрешая только те, у которых есть разрешения на расшифровку и чтение.

- [Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Настройка команды с изоляцией для обеспечения безопасности](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Дополнительные ресурсы:

- [Сведения о метках конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Защита информации

Политики защиты от потери данных могут предотвратить случайный общий доступ к конфиденциальным сведениям в SharePoint, Exchange и Teams. Можно создавать политики, определяющие действия, выполняемые (например, блокировка доступа), на основе набора правил.

- [Общие сведения о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP в Microsoft Teams помогает защитить конфиденциальные данные в беседах и каналах в Teams, удаляя сообщения, содержащие конфиденциальную информацию.

- [Защита от потери данных и Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Если у вас есть конфиденциальные сведения, уникальные для вашей организации, такие как названия кода проекта, можно создать собственные типы конфиденциальной информации и применить их к политикам защиты от потери данных для защиты контента в группах, в Teams и SharePoint.

- [Пользовательские типы конфиденциальной информации](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Сегментация пользователей

С помощью информационных барьеров вы можете сегментировать данные и пользователей, чтобы ограничить нежелательное взаимодействие и совместную работу между группами и избежать конфликтов интересов в Организации. С помощью информационных препятствий можно создавать политики, чтобы разрешить или запретить совместную работу с файлами, беседы, звонки или приглашения на собрания между группами людей в вашей организации.

- [Информационные барьеры](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Информационные барьеры в Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Использование препятствий для работы с данными в SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Связанные статьи

[Безопасность и соответствие требованиям для Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Защита информации](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


