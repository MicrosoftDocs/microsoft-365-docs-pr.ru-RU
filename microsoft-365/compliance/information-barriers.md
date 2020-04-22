---
title: Сведения о барьерах информации
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Используйте информационные барьеры, чтобы обеспечить соответствие требованиям, используя Microsoft Teams в вашей организации.
ms.openlocfilehash: 344c2b6999a8fd890358a25b39ef3a37abc9ef58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636107"
---
# <a name="information-barriers"></a>Информационные барьеры

## <a name="overview"></a>Обзор

<!--

# Information barriers (click-through test)

## Overview



 [![Click-Through for Information Barriers](./media/information-barriers/clickthrough-information-barriers-thumbnail.png)](./media/information-barriers/clickthrough-information-barriers.pdf)


Click through an overview of Information Barriers: [PDF](./media/information-barriers/clickthrough-information-barriers.pdf) | [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/Clickthrough-Information-Barriers.pptx)

OLD: Move comment field here

 [![Click-Through for Information Barriers](./media/information-barriers/Clickthrough_InformationBarriers_Thumbnail.png)](./media/information-barriers/Clickthrough_InformationBarriers.pdf)

For the PowerPoint slide of this Click-Through, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/InfoBarriersExample.pptx).

>[!Tip]
>Try this new [Click-Through on information barriers](media/information-barriers/Clickthrough_InformationBarriers.pdf) for a quick overview of the essential facts.
>

--> 


Облачные службы Майкрософт включают мощные возможности общения и совместной работы. Однако предположим, что вы хотите ограничить связь между двумя группами, чтобы избежать конфликта интересов в вашей организации. Или, возможно, вы хотите ограничить связь между определенными пользователями в Организации, чтобы защитить внутреннюю информацию. Microsoft 365 обеспечивает взаимодействие и совместную работу между группами и организациями, поэтому существует ли способ ограничения взаимодействия между определенными группами пользователей, когда это необходимо? С помощью информационных барьеров вы можете! 

На этом этапе можно выполнить развертывание, начиная с Microsoft Teams. Предполагая, что ваша [Подписка](#required-licenses-and-permissions) включает в себя барьеры информации, администратор соответствия требованиям или администратор по управлению данными может определять политики для разрешения или запрета связи между группами пользователей в Microsoft Teams. Политики барьера информации могут использоваться в следующих ситуациях:

- Пользователь в дне Trader Group не должен общаться с группой маркетинга
- Сотрудники отдела финансов, работающие с конфиденциальной информацией о компании, не должны общаться с определенными группами в Организации
- Внутренняя группа с коммерческими секретными материалами не должна звонить или общаться с людьми в определенных группах в Организации
- Справочная группа должна обращаться к сети или общаться только с другими участниками группы разработчиков продуктов

> [!IMPORTANT]
> Информационные барьеры ***поддерживают только*** два способа ограничения. Один из таких ограничений, например маркетинг, может общаться с днями недели, но день не ***может поддерживать обмен данными с маркетингом***.

Для всех приведенных ниже примеров сценариев (и более) можно определить политики информационных барьеров, чтобы запретить или разрешить взаимодействие в Microsoft Teams. Такие политики могут препятствовать абонентам звонить или общаться, которые им не нужны, или разрешить пользователям общаться только с определенными группами в Microsoft Teams. С действующими политиками для работы с информационными барьерами, когда пользователи, покрытые этими политиками, пытаются связаться с другими пользователями в Microsoft Teams, выполняются проверки, чтобы запретить (или разрешить) связь (как определено политиками барьера информации). Чтобы узнать больше о пользовательском интерфейсе с помощью барьеров информации, ознакомьтесь с разделом [Information барьеры в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!IMPORTANT]
> В настоящее время барьеры информации не применяются к сообщениям электронной почты или к общему доступу к файлам через SharePoint Online или OneDrive. Кроме того, барьеры информации не зависят от [ограничений на соответствие требованиям](set-up-compliance-boundaries.md).<p>Перед определением и применением политик барьера данных убедитесь, что в Организации не действуют [политики адресной книги Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) . (Барьеры на основе информации основаны на политиках адресных книг.) 

## <a name="what-happens-with-information-barriers"></a>Что происходит с барьерами информации

При наличии политик барьера информации пользователи, которые не должны общаться с другими пользователями, не смогут найти, выбрать, чат или позвонить этим пользователям. С помощью таких барьеров вы можете предотвратить несанкционированный обмен данными.

Изначально информационные барьеры применяются только к разговорам и каналам Microsoft Teams. В Microsoft Teams политики информационных барьеров определяют и предотвращают следующие виды неавторизованных коммуникаций.
- Поиск пользователя
- Добавление участника в группу
- Начало сеанса беседы с пользователем
- Начало сеанса групповой беседы
- Приглашение пользователя присоединиться к собранию
- Совместное использование экрана
- Размещение звонка 

Если вовлеченные люди включены в политику барьера информации для предотвращения действий, они не смогут продолжить работу. Кроме того, в Microsoft Teams можно блокировать связь всех пользователей, включенных в политику барьера информации. Если пользователи, затронутые политиками барьера информации, входят в одну и ту же команду или группу, они могут быть удалены из этих сеансов чата, а дальнейшие связи с группой могут быть не разрешены.

Чтобы узнать больше о пользовательском интерфейсе с помощью барьеров информации, ознакомьтесь с разделом [Information барьеры в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

## <a name="required-licenses-and-permissions"></a>Обязательные лицензии и разрешения

На этом этапе можно выполнить развертывание, а также включить в подписки следующие сведения:

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Защита информации и соответствие требованиям в Microsoft 365 E5

Дополнительные сведения [см.](https://products.office.com/business/security-and-compliance/compliance-solutions)

Чтобы [определить или изменить политики барьера данных](information-barriers-policies.md), необходимо назначить одну из следующих ролей:

- Глобальный администратор Microsoft 365
- Глобальный администратор Office 365
- Администратор соответствия требованиям
- Управление соответствием требованиям (это новая роль)

(Дополнительные сведения о ролях и разрешениях см. [в разделе разрешения в центре безопасности Office 365 & соответствия требованиям](../security/office-365-security/protect-against-threats.md).)

Вы должны быть знакомы с командлетами PowerShell, чтобы определить, проверить или изменить политики барьера данных. Хотя в [этой статье рассказывается о](information-barriers-policies.md)нескольких примерах командлетов PowerShell, необходимо знать дополнительные сведения, например параметры, для Организации.

## <a name="next-steps"></a>Дальнейшие действия

- [Дополнительные сведения об барьерах информации в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [Просмотр атрибутов, которые можно использовать для политик барьера информации](information-barriers-attributes.md)

- [Определение политик для барьеров информации](information-barriers-policies.md)

- [Изменение (или удаление) политик барьера информации](information-barriers-edit-segments-policies.md) 