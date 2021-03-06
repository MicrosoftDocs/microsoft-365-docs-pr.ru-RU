---
title: Управление сведениями, которые регулируются правилами конфиденциальности данных
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Используйте Microsoft 365 метки и политики хранения для управления личными данными в Microsoft 365 среде.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928440"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Управление сведениями, которые регулируются правилами конфиденциальности данных

Элементы управления информацией могут быть использованы в вашей среде для решения потребностей в соблюдении конфиденциальности данных, в том числе номера, которые специфичен для общего регулирования защиты данных (GDPR), HIPAA-HITECH (закон о конфиденциальности здравоохранения США), Закона о защите прав потребителей в Калифорнии (CCPA) и Закона о защите данных Бразилии (LGPD). 

Эти элементы управления в основном попадают в следующие области решения:

- Политики хранения
- Метки хранения
- Управление записями

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Правила конфиденциальности данных, влияющие на управление информацией

Вот пример списка правил конфиденциальности данных, которые могут относиться к средствам управления информацией:

- Статья GDPR (13)(2)(a)
- Статья GDPR (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(II))
- Статья 46 LGPD

Дополнительные сведения об этих правилах см. в статье Оценка рисков конфиденциальности данных и [определение конфиденциальной статьи.](information-protection-deploy-assess.md)

Для управления информацией правила конфиденциальности данных обычно выявят следующие требования:

- Следует использовать техническую схему хранения и удаления персональных данных, хранимых в Microsoft 365.
- Если вы собираетесь хранить персональные данные, сообщите субъекту о том, как долго будут храниться данные, что является стандартной практикой в настоящее время на передней веб-системы.
- Персональные данные должны быть защищены от случайной обработки, потери или изменения с помощью проверяемых методов.
- Любые действия, выполненные в отношении персональных данных, должны быть задокументированы, и эта документация должна храниться в течение указанного периода.

Поскольку правила конфиденциальности данных не являются очень конкретными для хранения и удаления данных, необходимо учитывать другие факторы, которые могут диктовать рекомендации по управлению данными для личной информации, хранимой в Microsoft 365 подписке. Вот несколько примеров:

- Старение учетных записей потребителей после 5 лет бездействия и требует удаления или анонимизации данных учетных записей после этого момента, что требует оркестровки между системой хранения данных и рабочего процесса, связанного с уведомлениями и другой автоматизацией.
- Настройка правил для хранения политик и процедур, связанных с GDPR, в течение трех лет после их изменения, что соответствует расписанию хранения политик и процедур организации.
- Ведение отдельной подписки для общения с потребителями через организацию поддержки. Все сообщения электронной почты были сохранены и удалены через две недели, чтобы уменьшить любое наращивание долгов конфиденциальности в системе.

Ключевой вопрос, на который нужно ответить: 

- Как долго необходимо хранить информацию, содержащую персональные данные, по веские бизнес-причинам, чтобы избежать практики "хранить ее навсегда"? Это необходимо уравновешить с потребностями хранения для непрерывности бизнеса.

Независимо от юридических и бизнес-причин хранения или удаления персональных данных корпорация Майкрософт предоставляет ряд возможностей для реализации схемы управления данными в Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Управление управлением информацией в Microsoft 365

Для начала см. [в](../compliance/manage-information-governance.md) Microsoft 365. Управление управлением информацией и хранением данных, удалением [и уничтожением](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)данных.

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Разработка расписания хранения данных для контейнеров, электронной почты и контента

Учитывайте следующее:

- Создание расписания хранения данных для определенных типов информации следует считать обязательным условием для реализации любой схемы хранения или удаления.

- Учитывая количество типов информации, которые большинство организаций считают важными, а также соответствующие большие графики хранения записей, которые идут вместе с ними, реализация стратегии управления хранением данных и записями требует планирования. 

- Ключ к созданию эффективной стратегии управления данными этого типа заключается в том, чтобы сосредоточиться на наиболее приоритетных бизнес-функциях и типах информации, которые требуют более формального управления. Примерами являются юридические контракты, финансовые отчеты и документация по нормативным требованиям. Старайтесь не иметь отдельного расписания хранения для каждого типа сведений. Попробуйте максимально использовать общие категории, например, с графиками хранения 7 лет для общего бизнес-контента.

- После того как типы персональных данных в вашей среде будут лучше известны, создайте графики хранения и удаления этого типа контента и отрегулируете архитектуру информации, чтобы упростить управление данными. Например, изолировать личную информацию на отдельных сайтах, библиотеках или папках с контролируемым доступом.

### <a name="retention-policies-and-retention-labels"></a>Политики и метки хранения

Используйте [политики хранения и метки](../compliance/retention.md) хранения для сохранения или удаления контента в Microsoft 365, который содержит или, как ожидается, содержит персональные данные.

### <a name="records-management"></a>Управление записями

Используйте метки хранения, которые объявляют контент записью, для реализации [решения](../compliance/records-management.md) по управлению записями для данных в Microsoft 365.

Для конфиденциальности данных запросы субъекта данных (DSRs), полученные юридическим отделом, объявляются записью и могут храниться бесконечно или утилизироваться с доказательствами, чтобы придерживаться спецификаций хранения нормативных действий.