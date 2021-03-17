---
title: Параметры соответствия требованиям для групп Microsoft 365, Teams и Совместной работы SharePoint
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
description: Узнайте о параметрах соответствия требованиям для групп Microsoft 365, Teams и SharePoint.
ms.openlocfilehash: f68381ab45e74b9b7c8f44465387add82bd4150a
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838655"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Параметры соответствия требованиям для групп Microsoft 365, Teams и Совместной работы SharePoint

Microsoft 365 предлагает полный набор инструментов для обеспечения соответствия требованиям по мере совместной работы пользователей. Просмотрите эти параметры и рассмотрите, как они соедино с потребностями бизнеса, чувствительностью данных и областью пользователей, с которых необходимо сотрудничать.

В следующей таблице приводится быстрая ссылка на элементы управления соответствием требованиям, доступные в Microsoft 365. Дополнительные сведения предоставляются в следующих разделах.

|Категория|Описание|Справочные материалы|
|:-------|:----------|:--------|
|Хранение сведений|||
||Сохранение групп почты и контента SharePoint|[Узнайте о политиках хранения для SharePoint и OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Сохранение чата и сообщений|[Узнайте о политиках хранения для Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Классификация сведений|||
||Классификация групп и групп|[Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Автоматически классифицировать конфиденциальный контент|[Автоматическое применение метки конфиденциальности к содержимому](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Шифрование конфиденциального контента|[Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Защита информации|||
||Предотвращение потери конфиденциальной информации|[Общие сведения о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Защита конфиденциальной информации в чате.|[Предотвращение потери данных и Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Определение конфиденциальных сведений организации|[Пользовательские типы конфиденциальной информации](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Сегментация пользователей|||
||Ограничение связи между сегментами пользователей|[Информационные барьеры](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Хранение сведений

Политики хранения доступны для хранения или удаления элементов, используемых для совместной работы в группах и группах, включая файлы, сообщения и почту. Политики можно установить для сохранения и удаления, только для сохранения или удаления. Информация, охватываемая политикой хранения, защищена в случае истечения срока действия группы или группы или иного удаления.

Настройка политики хранения для Microsoft 365 Groups охватывает почтовый ящик группы и связанный сайт и файлы SharePoint.

- [Узнайте о политиках хранения для SharePoint и OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Политики хранения для Teams сохраняют сообщения чата и канала. Хотя сообщения чата и канала хранятся в почтовых ящиках Exchange, политики хранения Exchange не влияют на них. Необходимо настроить политики хранения для применения к чатам Teams и сообщениям каналов Teams. 

Пользовательские чаты сохраняются на неопределенный срок, даже если учетная запись пользователя удалена. Если вы не хотите хранить эти данные бесконечно, рассмотрите возможность использования политики хранения для удаления пользовательских чатов после указанного времени или включите это удаление в процесс удаления пользователя.

- [Узнайте о политиках хранения для Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Политики хранения в Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

В сообщениях каналов Microsoft 365 Groups, Teams chat и Teams может быть установлена единая политика хранения. 

Дополнительные ресурсы:

- [Сведения о политиках хранения](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Теги хранения и политики хранения в](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) Exchange

## <a name="information-classification"></a>Классификация сведений

Метки конфиденциальности можно использовать для управления гостевом доступом, конфиденциальностью групп и команд, а также доступом неуправляемых устройств для групп и групп. Применяя метку, эти параметры автоматически настраиваются в зависимости от параметров метки.

- [Используйте метки конфиденциальности, чтобы защитить контент в Microsoft Teams, в группах Microsoft 365 и на сайтах SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Вы можете настроить Microsoft 365 для автоматического применения меток чувствительности к файлам и электронным письмам на основе установленных критериев, включая обнаружение типов конфиденциальной информации или шаблонов, совпадающих с классифицируемыми классификаторами.

- [Автоматическое применение метки конфиденциальности к содержимому](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Для шифрования файлов можно использовать метки конфиденциальности, позволяющие расшифровывать и читать только те, у кого есть разрешения.

- [Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Настройка команды с изоляцией для обеспечения безопасности](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Дополнительные ресурсы:

- [Сведения о метках конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Защита информации

Политики DLP могут предотвратить случайный обмен конфиденциальной информацией в SharePoint, Exchange и Teams. Можно создать политики, которые указывают действия, которые необходимо принять (например, заблокировать доступ) на основе набора правил.

- [Общие сведения о защите от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP в Teams может помочь защитить конфиденциальные сведения в чате Teams и сообщениях каналов, удалив сообщения, содержащие конфиденциальную информацию.

- [Предотвращение потери данных и Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Если у вас есть конфиденциальные сведения, уникальные для вашей организации, например имена кодов проектов, вы можете создать собственные типы конфиденциальных сведений и применить их к политикам DLP для защиты контента в группах, группах и Sharepoint.

- [Пользовательские типы конфиденциальной информации](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Сегментация пользователей

С помощью информационных барьеров можно сегментировать данные и пользователей, чтобы ограничить нежелательное общение и совместную работу между группами и избежать конфликтов интересов в организации. Информационные барьеры позволяют создавать политики, позволяющие или препятствующие совместной работе с файлами, чату, вызову или собранию приглашений между группами людей в организации.

- [Информационные барьеры](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Информационные барьеры в Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Использование информационных барьеров в SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Родственные темы

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)

[Безопасность и соответствие требованиям для Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Защита информации](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
