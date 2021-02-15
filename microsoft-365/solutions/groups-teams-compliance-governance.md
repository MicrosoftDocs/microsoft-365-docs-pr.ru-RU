---
title: Варианты соответствия требованиям для групп Microsoft 365, Teams и совместной работы SharePoint
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Узнайте о вариантах обеспечения соответствия требованиям для групп Microsoft 365, Teams и совместной работы SharePoint.
ms.openlocfilehash: e1ca6e638b2d44ae3b04e2a0f13222424e89714d
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613634"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Варианты соответствия требованиям для групп Microsoft 365, Teams и совместной работы SharePoint

Microsoft 365 предлагает полный набор средств для обеспечения соответствия требованиям по мере совместной работы пользователей. Просмотрите эти параметры и подумайте, как они соедиряду с вашими бизнес-потребностями, конфиденциальность данных и областью пользователей, с которых должны работать ваши пользователи.

В следующей таблице приводится краткий справочник по средствам контроля соответствия требованиям, доступным в Microsoft 365. Дополнительные сведения предоставляются в следующих разделах.

|Категория|Описание|Справка|
|:-------|:----------|:--------|
|Хранение информации|||
||Сохранение почты групп и содержимого SharePoint|[Узнайте о политиках хранения для SharePoint и OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Сохранение чата и сообщений|[Узнайте о политиках хранения для Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Классификация информации|||
||Классификация групп и команд|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Автоматическое классификация конфиденциального содержимого|[Автоматическое применение метки конфиденциальности к содержимому](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Шифрование конфиденциального содержимого|[Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Защита информации|||
||Предотвращение потери конфиденциальной информации|[Общие сведения о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Защита конфиденциальной информации в чате.|[Предотвращение потери данных и Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Определение конфиденциальной информации организации|[Пользовательские типы конфиденциальной информации](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Сегментация пользователей|||
||Ограничение взаимодействия между сегментами пользователей|[Информационные барьеры](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Хранение информации

Политики хранения доступны для хранения или удаления элементов, используемых для совместной работы в группах и командах, включая файлы, сообщения и почту. Политики можно настроить для сохранения и удаления, только для сохранения или удаления. Сведения, на которые распространяется политика хранения, защищены в случае истечения срока действия группы или команды или иным образом.

Настройка политики хранения для групп Microsoft 365 охватывает почтовый ящик группы, связанный сайт и файлы SharePoint.

- [Узнайте о политиках хранения для SharePoint и OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Политики хранения Для Teams сохраняют сообщения чата и каналов. Хотя сообщения чата и канала хранятся в почтовых ящиках Exchange, на них не влияют политики хранения Exchange. Необходимо настроить политики хранения для применения к чатам Teams и сообщениям каналов Teams:

- [Узнайте о политиках хранения для Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Политики хранения в Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Одну политику хранения можно настроить для применения к группам Microsoft 365, чатам Teams и каналам Teams. 

Дополнительные ресурсы:

- [Сведения о политиках хранения](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Теги хранения и политики хранения](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) в Exchange

## <a name="information-classification"></a>Классификация информации

Метки конфиденциальности можно использовать для управления гостевых доступом, конфиденциальностью групп и команд, а также доступом неуправляемых устройств для групп и команд. При применении метки эти параметры настраиваются автоматически, как указано в параметрах метки.

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Вы можете настроить Microsoft 365 для автоматического применения меток конфиденциальности к файлам и электронным письмам на основе занижаемых критериев, включая обнаружение типов конфиденциальной информации или соответствия шаблонов обучаемым классификаторам.

- [Автоматическое применение метки конфиденциальности к содержимому](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Вы можете использовать метки конфиденциальности для шифрования файлов, позволяя расшифровывать и считывать их только тем пользователям, у которых есть разрешения.

- [Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Настройка команды с изоляцией для обеспечения безопасности](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Дополнительные ресурсы:

- [Сведения о метках конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Защита информации

Политики DLP могут предотвратить случайное совместное использование конфиденциальной информации в SharePoint, Exchange и Teams. Можно создать политики, которые определяют действия, которые необходимо принять (например, блокирование доступа), на основе набора правил.

- [Общие сведения о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP в Teams может помочь защитить конфиденциальную информацию в сообщениях чатов и каналов Teams, удалив сообщения, содержащие конфиденциальную информацию.

- [Предотвращение потери данных и Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Если у вас есть конфиденциальную информацию, уникальную для вашей организации, например имена кодов проектов, вы можете создать собственные типы конфиденциальной информации и применить их к политикам защиты от защите данных для защиты контента в группах, группах и Sharepoint.

- [Пользовательские типы конфиденциальной информации](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Сегментация пользователей

С помощью информационных барьеров можно сегментировать данные и пользователей, чтобы ограничить нежелательные коммуникации и совместную работу между группами и избежать конфликтов интересов в организации. Информационные барьеры позволяют создавать политики, позволяющие разрешить или запретить совместную работу с файлами, чат, вызовы или приглашения на собрания между группами людей в организации.

- [Информационные барьеры](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Информационные барьеры в Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Использование информационных барьеров с SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Связанные статьи

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Безопасность и соответствие требованиям для Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Защита информации](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
