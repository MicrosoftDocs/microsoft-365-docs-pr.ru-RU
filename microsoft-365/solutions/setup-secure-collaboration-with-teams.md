---
title: Настройка безопасной совместной работы с помощью Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
recommendations: false
description: Узнайте, как настроить совместную работу с защищенным контентом в Teams для защиты данных в зависимости от их конфиденциальности.
ms.openlocfilehash: 7a5b8f58cc5e4a23d2d143419f99ecdd87b949c1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924363"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>Настройка безопасной совместной работы с Microsoft 365 и Microsoft Teams

Возможность легкого обмена информацией с нужными людьми, а также предотвращение oversharing является ключом к успеху организации. Это включает возможность безопасного обмена конфиденциальными данными только с теми, кто должен иметь к ним доступ. В зависимости от проекта это может включать обмен конфиденциальными данными с людьми за пределами организации.

Это руководство по решению совместной работы включает два компонента, которые помогут вам:
- Развертывание Microsoft Teams с правильным уровнем защиты для каждого проекта
- Настройка внешнего общего доступа с соответствующими настройками безопасности для каждого проекта

![Развертывание Teams с соответствующей защитой и настройка внешнего общего доступа с соответствующими настройками безопасности](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Если универсальные и простые в использовании средства совместной работы с контентом недоступны, пользователи часто будут совместно работать с документами по электронной почте. Это утомительный и подверженный ошибкам метод совместной работы, который может повысить риск ненадлежащего обмена информацией. Если людям слишком сложно обмениваться информацией, они могут вернуться к использованию потребительских продуктов, не управляемых ИТ. Это может представлять еще более высокий риск.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

С Microsoft 365 можно развернуть Teams с помощью различных конфигураций, которые помогают:

- Защита интеллектуальной собственности
- Включить простой способ совместной работы
- Создание баланса между безопасностью и удобностью, что повышает удовлетворенность пользователей и снижает риск теневых ИТ-служб

Большинство организаций имеют разнообразные сведения с различной степенью чувствительности и различной степенью влияния на бизнес, если информация ненадлежащим образом передается. В зависимости от чувствительности данного фрагмента информации может потребоваться разрешить общий доступ к:

- Любой (неавентированный)
- Люди внутри организации
- Конкретные люди в организации
- Конкретные люди в организации и за ее пределами

Такие сведения, как маркетинговые брошюры, предназначены для широкого доступа за пределами организации. Такие сведения, как меню кафетериев, не предназначены для внешнего обмена, но не влияют на бизнес, если они были общими внешне. Эти типы информации практически не нуждаются в защите.

Эти же маркетинговые брошюры, пока находятся в стадии разработки, могут быть общими только внутри организации. В этом случае параметров общего доступа по умолчанию в Teams может быть достаточно.

Сведения о новом продукте, который находится на стадии разработки, могут считаться конфиденциальными даже в организации. В этом случае может быть целесообразно использовать более высокую степень защиты. Например, можно ограничить доступ к этой информации членам определенной группы. В зависимости от проекта вам может потребоваться сотрудничать с людьми, не в рамках организации, например с поставщиком или организацией-партнером.

Информация, которая имеет решающее значение для успеха вашей организации или имеет строгие требования к безопасности или требованиям соответствия требованиям, может требовать еще более высоких уровней защиты.

![Шкала риска от низкой (выпущенной брошюры) до высокой (конфиденциальные бизнес-данные)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Для всех сценариев, отмеченных выше, можно использовать группы в Microsoft Teams для хранения, обмена и совместной работы с информацией. 

Для настройки безопасной совместной работы используйте эти Microsoft 365 и функции.

| Продукт или компонент | Возможность или функция | Лицензирование |
|:-------|:-----|:-------|
| Microsoft Defender для Office 365 | Сейф Вложения для SPO, OneDrive и Teams; Сейф Документы; Сейф Ссылки для Teams    | Microsoft 365 E1, E3 и E5 |
| SharePoint    | Политики общего доступа к сайтам и файлам, разрешения на совместное использование сайтов, ссылки на общий доступ, запросы на доступ, параметры гостевых сайтов | Microsoft 365 E1, E3 и E5 |
| Microsoft Teams   | Гостевой доступ, частные команды, частные каналы | Microsoft 365 E1, E3 и E5 |
| Соответствие требованиям Microsoft 365  | Метки конфиденциальности    | Microsoft 365 E3 и E5 |

### <a name="collaboration-governance"></a>Управление совместной работой

Microsoft 365 предоставляет множество вариантов управления решением совместной работы. Мы рекомендуем использовать этот контент [](collaboration-governance-overview.md) развертывания вместе с контентом управления совместной работой для создания наилучшего решения совместной работы для вашей организации.

### <a name="using-teams-for-all-kinds-of-data"></a>Использование Teams для всех видов данных

Для управления доступом к информации с различными чувствительностями мы разработали три различных уровня защиты для [Teams.](configure-teams-three-tiers-protection.md) Вы можете настроить любой из этих уровней для лучшего решения потребностей или бизнеса. 

![Графика трех уровней защиты для Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Эти уровни *—* *базовые,* чувствительные и высокочувствительные *—* постепенно увеличивают защиты, которые помогают предотвратить чрезмерное и потенциальное утечки информации, как показано в следующей таблице.

|-|**Базовый уровень**|**Чувствительный уровень**|**Высокочувствительный уровень**|
|:--|:-----------|:------------|:-------------------|
|Общественная или частная группа|Либо|Частный|Частный|
|Общий доступ без проверки подлинности|Заблокировано|Заблокировано|Заблокировано|
|Общий доступ к файлам|Разрешено|Разрешено|Делиться могут только владельцы команд.|
|Членство в команде|Присоединиться к общедоступным командам может любой желающий.<br>Утверждение владельца команды, необходимое для принятия в частные группы.|Утверждение владельца команды, необходимое для принятия.|Утверждение владельца команды, необходимое для принятия.|
|Шифрование документов|||Доступно с меткой конфиденциальности|
|Предоставление общего доступа гостям|Разрешено|Может быть разрешено или заблокировано|Может быть разрешено или заблокировано|
|Неуправляемые устройства|Нет ограничений|Доступ только на веб-сайте|Заблокировано|

Настройка этих уровней включает в себя:

- Настройка параметров в Teams для гостевого доступа и частных каналов
- Настройка параметров на связанном веб-сайте SharePoint для внутреннего и гостевого доступа, запросов на доступ и обмена ссылками
- Для *чувствительных и* высокочувствительных уровней настройка меток конфиденциальности для классификации групп и управления гостем и доступом с неугодных устройств 
- Для *высокочувствительного* уровня настройка метки конфиденциальности для шифрования документов, к которым она применяется

Начните с базового уровня, а  затем  добавьте группы, которые используют конфиденциальные и высокочувствительные уровни, необходимые для защиты информации в организации. Чтобы начать работу, см. в этих ресурсах:

- [Настройка команд с базовым уровнем защиты](configure-teams-baseline-protection.md)
- [Настройте группы с защитой для конфиденциальных данных](configure-teams-sensitive-protection.md)
- [Настроить группы с защитой для конфиденциальных данных](configure-teams-highly-sensitive-protection.md)

Если у вас есть высокочувствительный проект, который требует дополнительной защиты от общего доступа даже в вашей организации, вы можете настроить команду, которая использует собственную метку чувствительности для шифрования файлов, чтобы только члены группы могли читать их. Подробнее [см. в материале Configure a team with security isolation.](secure-teams-security-isolation.md)

### <a name="sharing-with-people-outside-your-organization"></a>Общий доступ к людям за пределами организации

Возможно, вам потребуется обмениваться сведениями о [любой конфиденциальности с людьми за пределами вашей организации.](collaborate-with-people-outside-your-organization.md) Это может варьироваться от общего доступа к одному документу с одним человеком до совместной работы над крупным проектом с крупной организацией-партнером или фрилансерами со всего мира. В Microsoft 365 этот диапазон внешнего обмена можно легко сделать и с помощью соответствующих гарантий, чтобы защитить конфиденциальной информации.

Эти ресурсы помогут вам начать работу с настройкой среды для совместной работы с людьми за пределами организации:

- [Совместное использование документов для](collaborate-on-documents.md) обмена отдельными файлами папок.
- [Совместная работа на сайте](collaborate-in-site.md) для совместной работы с гостями на SharePoint сайте.
- [Совместная работа в команде](collaborate-as-team.md) для совместной работы с гостями в команде.

В зависимости от конфиденциальности общих сведений можно добавить меры предосторожности, которые помогут предотвратить переохвачение. Эти ресурсы помогут настроить необходимые для организации средства защиты:

- [Рекомендации по предоставлению общего доступа к файлам и папкам непроверенным пользователям](best-practices-anonymous-sharing.md)
- [Ограничьте случайное воздействие файлов при обмене с людьми за пределами вашей организации](share-limit-accidental-exposure.md)
- [Создание безопасной среды гостевого общего доступа](create-secure-guest-sharing-environment.md)

Если у вас есть крупный проект с организацией-партнером, вы можете использовать Azure Entitlement Management для управления гостями из этой организации в команде, которую вы создали для проекта. Дополнительные сведения см. в материале [Create a B2B extranet with managed guests.](b2b-extranet.md)



## <a name="training-for-administrators"></a>Обучение администраторов

Эти учебные модули из Microsoft Learn помогут вам изучить функции совместной работы, управления и удостоверений в Teams и SharePoint.

#### <a name="teams"></a>Teams

|Обучение:|Управление совместной работой команды с помощью Microsoft Teams|
|:---|:---|
|![Teams значок подготовки к совместной работе](../media/manage-team-collaboration-with-microsoft-teams.svg)|Управляя совместной работой команды с помощью Microsoft Teams, вы ознакомитесь с функциями и возможностями Microsoft Teams, центра совместной работы в Microsoft 365. Вы узнаете, как использовать Teams для упрощения совместной работы и связи в организации, локально и за ее пределами, на различных устройствах (настольных компьютерах, планшетах, телефонах), применяя все разнообразие функций приложений Office 365. Вы поймете, каким образом Teams обеспечивает комплексную и гибкую среду для совместной работы в разных приложениях и на разных устройствах. Эта схема обучения поможет вам подготовиться к сертификации Сертификат Microsoft 365: помощник администратора Teams.<br><br>2 часа 17 минут — путь обучения — 5 модулей|

> [!div class="nextstepaction"]
> [Начало >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Обучение:|Совместная работа с использованием SharePoint в Microsoft 365|
|:---|:---|
|![SharePoint значок обучения](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|В статье, посвященной управлению общим контентом с помощью Microsoft SharePoint, рассказывается о функциях и возможностях SharePoint, а также о том, как этот продукт работает с Microsoft 365. Вы узнаете о различных типах сайтов SharePoint (в том числе о центральных сайтах), а также о функциях защиты данных, составления отчетов и мониторинга. Вы также узнаете, как с помощью функции общего доступа к файлам и папкам в SharePoint оптимизировать совместную работу, как предоставлять внешний доступ к файлам и как управлять сайтами SharePoint в Центре администрирования SharePoint. Эта схема обучения поможет вам подготовиться к сертификации Сертификат Microsoft 365: помощник администратора по командной работе.<br><br>1 час 14 мин . Путь к обучению — 4 модуля|

> [!div class="nextstepaction"]
> [Начало >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Защита информации

|Обучение:|Защита корпоративной информации с помощью Microsoft 365|
|:---|:---|
|![Teams значок подготовки по защите информации](../media/protect-enterprise-information-microsoft-365.svg)|Защитить информацию организации стало сложнее, чем когда-либо. В схеме обучения Защита корпоративной информации с помощью Microsoft 365 рассматривается, как защитить конфиденциальную информацию от непреднамеренного разглашения или несанкционированного использования, как обнаруживать или классифицировать данные, как защитить их с помощью меток конфиденциальности, а также как отслеживать и анализировать конфиденциальную информацию для защиты от ее потери. Этот путь обучения поможет вам подготовиться к сертификации Microsoft 365: помощник администратора безопасности и Microsoft 365 сертификации: Enterprise администрирования экспертов..<br><br>1 час — путь обучения — 5 модулей|

> [!div class="nextstepaction"]
> [Начало >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Удостоверение и доступ

|Обучение:|Защита удостоверений и доступа в Azure Active Directory|
|:---|:---|
|![Значок подготовки удостоверений и доступа](../media/protect-identity-and-access-with-microsoft-365.svg)|В обучающей статье Удостоверение и доступ рассматриваются новейшие технологии удостоверений и доступа, средства для усиления проверки подлинности и рекомендации по защите удостоверений вашей организации. Технологии удостоверений и доступа Майкрософт позволяют защитить удостоверение организации, локально и в облаке, а также обеспечить безопасную работу пользователей откуда угодно. Эта схема обучения поможет вам подготовиться к сертификациям Сертификат Microsoft 365: помощник администратора безопасности и Сертификат Microsoft 365: эксперт по корпоративному администрированию.<br><br>2 часа 52 минуты — путь обучения — 6 модулей|

> [!div class="nextstepaction"]
> [Начало >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Обучение пользователей

Эти учебные модули могут помочь пользователям использовать Teams, группы и SharePoint для совместной работы Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Настройка и настройка значка подготовки команды](../media/set-up-customize-team-training.png)<br>**[Настройка и настройка команды](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint и синхронизировать значок обучения](../media/sharepoint-share-sync-training.png)<br>**[Совместное и синхронизированное](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams и найти значок подготовки файлов](../media/smc-teams-upload-find-files-training.png)<br>**[Upload и поиск файлов](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Совместное взаимодействие в командах и значке каналов](../media/teams-collaborate-channels-training.png)<br>**[Сотрудничество в командах и каналах](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>Иллюстрации

Эти иллюстрации помогут вам понять, как группы и группы взаимодействуют с другими службами в Microsoft 365 и какие функции управления и соответствия требованиям доступны для управления этими службами в вашей организации.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Группы в Microsoft 365 для ИТ-архитекторов
Что следует знать ИТ-архитекторам о группах в Microsoft 365

|**Item**|**Описание**|
|:-----|:-----|
|[![Эскиз инфографики групп](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Обновление: июнь 2019 г.|На этих иллюстрациях подробно показаны разные типы групп, как они создаются и управляются, а также приводится несколько рекомендаций по управлению.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams и связанные службы повышения производительности в Microsoft 365 для ИТ-архитекторов
Логическая архитектура служб повышения производительности в Microsoft 365, начиная с Microsoft Teams.

|**Item**|**Описание**|
|:-----|:-----|
|[![Эскиз плаката логической архитектуры Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Обновление: апрель 2019 г.   |Корпорация Майкрософт предоставляет набор служб повышения производительности, которые взаимодействуют между собой, обеспечивая возможности совместной работы для управления данными, безопасности и соответствия требованиям. <br/> <br/>Этот набор иллюстраций демонстрирует логическую архитектуру служб повышения производительности для корпоративных архитекторов, начиная с Microsoft Teams.|

## <a name="deploy-the-secure-collaboration-solution"></a>Развертывание безопасного решения совместной работы

Когда вы будете готовы к развертыванию этого решения, продолжайте следующие действия:
1. Настройка трех [различных уровней](configure-teams-three-tiers-protection.md)защиты для Teams .
2. Настройка параметров для обмена сведениями о любой конфиденциальности с [людьми за пределами организации.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>См. также

[Документация по безопасности Microsoft 365](../security/index.yml)

[Документация Microsoft 365 по соответствию требованиям](../compliance/index.yml)

[Знакомство с Microsoft Teams](/MicrosoftTeams/Teams-overview)
