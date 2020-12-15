---
title: Архивация сторонних данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как импортировать сторонние данные из платформ социальных сетей, платформ обмена мгновенными сообщениями и платформ для совместной работы с документами в почтовые ящики Microsoft 365.
ms.openlocfilehash: 42835d103e027bd63687151554f811dc0945d46f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682620"
---
# <a name="archive-third-party-data"></a>Архивация сторонних данных

Microsoft 365 позволяет администраторам использовать соединители данных для импорта и архивации сторонних данных с платформ социальных сетей, платформ обмена мгновенными сообщениями и платформ для совместной работы с документами в почтовые ящики в организации Microsoft 365. Одно из основных преимуществ использования соединители данных для импорта и архива сторонних данных в Microsoft 365 — возможность применения различных решений для обеспечения соответствия требованиям Microsoft 365 после импорта. Это помогает обеспечить соответствие данных вашей организации, не относясь к майкрософт, нормативным требованиям и стандартам, влияющим на вашу организацию.

## <a name="third-party-data-connectors"></a>Соединители данных сторонних производителей

В следующей таблице перечислены сторонние соединители данных, доступные в Центре соответствия требованиям Microsoft 365. В таблице также водятся решения для обеспечения соответствия требованиям, которые можно применить к сторонним данным после импорта и архива в Microsoft 365. Более [подробное описание каждого](#overview-of-compliance-solutions-that-support-third-party-data) решения для обеспечения соответствия требованиям и преимущества сторонних данных см. в следующем разделе.

> [!TIP]
> Щелкните ссылку  в столбце сторонних данных, чтобы перейти к пошаговой инструкции по созданию соединители для этого типа данных.

|Сторонние данные  |Судебное удержание|Обнаружение электронных данных  |Параметры хранения  |Управление записями  |Соответствие требованиям к обмену данными  |Управление внутренними рисками  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Сообщение Bloomberg](archive-bloomberg-message-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[Корпоративный номер <sup>1</sup>](archive-enterprise-number-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Отдел кадров](import-hr-data.md) ||||||![Галочка](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[Ms SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[O2 Network <sup>1</sup>](archive-o2-network-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Физические плохое состояние](import-physical-badging-data.md) ||||||![Галочка](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[<sup>Ветвь 2</sup>](archive-symphony-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Текстовый делегированный <sup>2</sup>](archive-text-delimited-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[Сеть Verizon <sup>1</sup>](archive-verizon-network-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Веб-страницы <sup>2</sup>](archive-webpagecapture-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[Workplace from Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|||
|[Масштабирование <sup>собраний 2</sup>](archive-zoommeetings-data.md)     |![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)|![Галочка](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1.</sup> Соединители данных, предоставляемые TeleMessage. Прежде чем архивировать данные в Microsoft 365, необходимо работать с TeleMessage, чтобы настроить службу архивизации для вашей организации. Дополнительные сведения см. в разделе необходимых условий в пошаговом инструкции для этого типа данных.<br/><br/><sup>2.</sup> Соединители данных, предоставляемые globanet. Прежде чем архивировать данные в Microsoft 365, необходимо вместе с Globanet настроить службу архивизации для вашей организации. Дополнительные сведения см. в разделе необходимых условий в пошаговом инструкции для этого типа данных.

Данные сторонних пользователей, перечисленные в предыдущей таблице (за исключением данных о персонале и физических данных о плохом качестве), импортируются в почтовые ящики пользователей. Соответствующие решения для обеспечения соответствия требованиям, которые поддерживают сторонние данные, применяются к почтовому ящику пользователя, в котором хранятся данные.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Обзор решений для обеспечения соответствия требованиям, которые поддерживают сторонние данные

В следующих разделах описаны некоторые из вещей, которые решения для обеспечения соответствия требованиям Microsoft 365 могут помочь вам управлять сторонними данными, перечисленными в предыдущей таблице.

### <a name="litigation-hold"></a>Судебное удержание

Для хранения [сторонних данных](create-a-litigation-hold.md) в почтовом ящике пользователя необходимо на удержание для судебного разбирательства. При создании удержания можно указать срок хранения (также называемый удержанием на основе времени), чтобы удаленные и измененные сторонние данные сохранялась в течение указанного периода, а затем окончательно удалялись из почтового ящика. Вы также можете хранить содержимое неопределенное время (называемое бесконечным удержанием) или до тех пор, пока удержание для судебного разбирательства не будет снято.

### <a name="ediscovery"></a>Обнаружение электронных данных

Три основных средства eDiscovery в Microsoft 365: поиск контента, основное eDiscovery и Advanced eDiscovery.

- **[Поиск контента.](content-search.md)** Средство поиска контента можно использовать для поиска импортируемых сторонних данных в почтовых ящиках. Вы можете использовать поисковые запросы и условия, чтобы сузить результаты поиска и экспортировать результаты поиска.

- **[Основное eDiscovery](get-started-core-ediscovery.md).** Это средство построено на базовых функциях поиска и экспорта, позволяя создавать случаи, позволяющие контролировать, кто может получать доступ к данным дела, удерживать почтовые ящики пользователей или содержимое почтовых ящиков, которое соответствует условиям поиска. Это означает, что вы можете на удержание при обнаружении электронных данных сторонних пользователей, импортируемых в почтовые ящики пользователей.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Это мощное средство расширяет возможности основных функций обнаружения электронных данных, позволяя добавлять хранителей в дело, помещая данные хранителя на хранение, а затем загружая сторонние данные хранителя в обзор для дальнейшего анализа, например тем и повторяют обнаружение. После загрузки сторонних данных в набор для проверки можно запросить и отфильтровать их по узкому набору результатов.

   Как core eDiscovery, так и Advanced eDiscovery могут управлять сторонними данными, которые могут быть релевантны для юридических или внутренних расследований вашей организации.

### <a name="retention-settings"></a>Параметры хранения

Вы можете применить [политику](retention.md) хранения к почтовым ящикам пользователей, чтобы хранить и удалять сторонние данные (и другое содержимое почтовых ящиков) по истечении срока хранения. Политики хранения также можно использовать для удаления сторонних данных [](disposition.md) определенного возраста или с помощью меток хранения, чтобы инициировать проверку удаления по истечении срока хранения сторонних данных.

### <a name="records-management"></a>Управление записями

Функция [управления записями](records-management.md) в Microsoft 365 позволяет объявлять сторонние данные в качестве записи. Это могут сделать пользователи, которые применяют метку хранения, которая пометит сторонние данные в их почтовом ящике как запись. Кроме того, вы можете автоматически применять метки хранения, определяя конфиденциальную информацию, ключевые слова или типы контента в сторонних данных.

### <a name="communication-compliance"></a>Соответствие требованиям к обмену данными

Вы можете использовать [соответствие коммуникации](communication-compliance.md) для проверки сторонних данных, чтобы убедиться, что они соответствуют стандартам данных вашей организации. Это можно сделать, обнаруживая, записывая и принимая меры по исправлению недопустимых сообщений в организации. Например, вы можете отслеживать импортируемые сторонние данные на оскорбительные языки, конфиденциальную информацию и соблюдение нормативных требований.

### <a name="insider-risk-management"></a>Управление внутренними рисками

Сигналы от сторонних данных, например выборочные данные [](insider-risk-management.md) о персонале, могут использоваться решением для управления внутренними рисками для минимизации внутренних рисков, позволяя обнаруживать, исследовать и действовать над рискованными действиями в организации. Например, данные, импортируемые соединитетелем данных отдела кадров, используются в качестве индикаторов риска для обнаружения кражи данных сотрудников.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Работа с партнером Майкрософт по архивам сторонних данных

Другой вариант импорта и архивизации сторонних данных — работа вашей организации с партнером Майкрософт. Если соединители данных, доступные в Центре соответствия требованиям Майкрософт, не поддерживают сторонние типы данных, вы можете сотрудничать с партнером, который может предоставить настраиваемый соединититель, который будет настраиваться для регулярного извлечения элементов из стороннего источника данных, а затем подключаться к Microsoft Cloud с помощью стороннего API и импортировать эти элементы в Microsoft 365. Партнерский соединититель также преобразует содержимое элемента из стороннего источника данных в сообщение электронной почты, а затем импортирует его в почтовый ящик в Microsoft 365.

Список партнеров, с которые вы можете работать, и пошаговой процесс для этого метода см. в подовой работе с партнером по архивации сторонних данных [в Microsoft 365.](work-with-partner-to-archive-third-party-data.md)
