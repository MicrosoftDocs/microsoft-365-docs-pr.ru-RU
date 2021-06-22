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
description: Узнайте, как импортировать сторонние данные с платформ социальных сетей, платформ обмена мгновенными сообщениями и платформ совместной работы с документами в Microsoft 365 почтовых ящиков.
ms.openlocfilehash: a0c4505d3fbd593f5703f4abfb5cba1870c037c5
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054778"
---
# <a name="archive-third-party-data"></a>Архивация сторонних данных

Microsoft 365 позволяет администраторам использовать соединители данных для импорта и архивации сторонних данных с платформ социальных сетей, платформ обмена мгновенными сообщениями и платформ совместной работы с документами в почтовые ящики Microsoft 365 организации. Одним из основных преимуществ использования соединители данных для импорта и архива сторонних данных в Microsoft 365 является возможность применения различных Microsoft 365 решений по обеспечению соответствия требованиям после импорта. Это позволяет убедиться, что данные организации, не в microsoft, не соответствует требованиям и стандартам, влияющим на организацию.

## <a name="third-party-data-connectors"></a>Соединители данных сторонних производителей

В следующей таблице перечислены сторонние соединители данных, доступные в Центр соответствия требованиям Microsoft 365. В таблице также подводятся итоги решений по обеспечению соответствия требованиям, которые можно применить к сторонним данным после импорта и архива в Microsoft 365. В следующем [разделе см.](#overview-of-compliance-solutions-that-support-third-party-data) более подробное описание каждого решения по соблюдению требований и способов его получения сторонними данными.

> [!TIP]
> Щелкните ссылку **в** столбце сторонних данных, чтобы пошаговую инструкцию по созданию соединитетеля для этого типа данных.

|Сторонние данные  |Удержание судебного разбирательства|Обнаружение электронных данных  |Параметры хранения  |Управление записями  |Соответствие требованиям к обмену данными  |Управление внутренними рисками  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Сеть <sup>Колокола 1</sup>](archive-bell-network-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Сообщение Bloomberg](archive-bloomberg-message-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Cisco Jabber на ms SQL <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Cisco Jabber на Oracle <sup>2</sup>](archive-ciscojabberonoracle-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Cisco Jabber на PostgreSQL <sup>2</sup>](archive-ciscojabberonpostgresql-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[Enterprise Номер <sup>1</sup>](archive-enterprise-number-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[FX Подключение <sup>2</sup>](archive-fxconnect-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Кадры (HR)](import-hr-data.md) ||||||![Флажок](../media/checkmark.png)
|[ICE Chat](archive-icechat-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[MS База данных SQL <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[O2 Network <sup>1</sup>](archive-o2-network-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Физическое плохое состояние](import-physical-badging-data.md) ||||||![Флажок](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Chatter Salesforce <sup>2</sup>](archive-salesforcechatter-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[Сигнал <sup>1</sup>](archive-signal-archiver-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Skype для бизнеса <sup>2</sup>](archive-skypeforbusiness-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Симфония <sup>2</sup>](archive-symphony-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Telegram <sup>1</sup>](archive-telegram-archiver-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Text-delimited <sup>2</sup>](archive-text-delimited-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Веб-страницы <sup>2</sup>](archive-webpagecapture-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[WeChat <sup>1</sup>](archive-wechat-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Рабочее место из Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
|[Масштабирование <sup>собраний 2</sup>](archive-zoommeetings-data.md)     |![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)|![Флажок](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Соединители данных, предоставляемые TeleMessage. Прежде чем архивировать данные в Microsoft 365, необходимо работать с TeleMessage, чтобы настроить службу архивизации для вашей организации. Дополнительные сведения см. в разделе Обязательное условие в пошаговом инструкции для этого типа данных. Соединители данных TeleMessage также доступны в GCC средах в облаке Microsoft 365 правительства США. Дополнительные сведения см. в разделе [Соединители](#data-connectors-in-the-us-government-cloud) данных в облачном разделе правительства США в этой статье. <br/><br/><sup>2</sup> Соединитель данных, предоставленный Veritas. Прежде чем архивировать данные в Microsoft 365, необходимо работать с Veritas, чтобы настроить службу архива для организации. Дополнительные сведения см. в разделе Обязательное условие в пошаговом инструкции для этого типа данных.

Сторонние данные, перечисленные в предыдущей таблице (за исключением данных о персонале и физических неустойки), импортируются в почтовые ящики пользователей. Соответствующие решения по обеспечению соответствия требованиям, поддерживающие сторонние данные, применяются к почтовому ящику пользователя, в котором хранятся данные.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Обзор решений по обеспечению соответствия требованиям, поддерживающая сторонние данные

В следующих разделах описаны некоторые из вещей, Microsoft 365 решения по обеспечению соответствия требованиям могут помочь вам управлять сторонними данными, перечисленными в предыдущей таблице.

### <a name="litigation-hold"></a>Удержание судебного разбирательства

Для хранения данных [сторонних пользователей](create-a-litigation-hold.md) в почтовом ящике пользователя в течение судебного разбирательства сохраняется удержание судебного разбирательства. При создании удержания можно указать продолжительность удержания (также называемую удержанием на основе времени), чтобы удаленные и измененные сторонние данные сохраняли в течение указанного периода, а затем окончательно удалялись из почтового ящика.  Или вы можете просто хранить контент на неопределенный срок (называется *бесконечным* удержанием) или до тех пор, пока удержание судебного разбирательства не будет удалено.

### <a name="ediscovery"></a>Обнаружение электронных данных

Три основных средства для поиска электронных Microsoft 365 — поиск контента, основные электронные поиски и Advanced eDiscovery.

- **[Поиск контента](content-search.md).** Средство поиска контента можно использовать для поиска почтовых ящиков для импортируемых сторонних данных. Вы можете использовать поисковые запросы и условия, чтобы сузить результаты поиска и экспортировать результаты поиска.

- **[Core eDiscovery](get-started-core-ediscovery.md).** Этот инструмент строится на базовых функциях поиска и экспорта, позволяя создавать случаи, позволяющие управлять, кто может получить доступ к данным дела, разместить удержание на почтовых ящиках пользователей или контенте почтовых ящиков, которые соответствуют критериям поиска. Это означает, что вы можете разместить удержание электронных данных на сторонних данных, импортируемых в почтовые ящики пользователей.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Этот мощный инструмент расширяет функции обнаружения основных электронных данных, позволяя добавлять хранителей в дело, помещая данные хранителя на удержание, а затем загружая сторонние данные хранителя в обзор для дальнейшего анализа, таких как темы и дублирование обнаружения. После загрузки сторонних данных в набор отзывов можно запрашивать и фильтровать их в узком наборе результатов.

   Как core eDiscovery, так и Advanced eDiscovery позволит управлять сторонними данными, которые могут иметь отношение к юридическим или внутренним расследованиям вашей организации.

### <a name="retention-settings"></a>Параметры хранения

Вы можете применить политику хранения [к](retention.md) почтовым ящикам пользователей для хранения и удаления сторонних данных (и другого контента почтовых ящиков) по истечении срока хранения. Вы также можете использовать политики хранения для удаления сторонних [](disposition.md) данных определенного возраста или использования меток хранения для запуска проверки диспозиции по истечении срока хранения сторонних данных.

### <a name="records-management"></a>Управление записями

Функция [управления записями](records-management.md) в Microsoft 365 позволяет объявлять сторонние данные записью. Это можно сделать вручную пользователями, которые применяют метку хранения, которая отмечает сторонние данные в почтовом ящике в качестве записи. Или вы можете автоматически применять метки хранения, определяя конфиденциальные сведения, ключевые слова или типы контента в сторонних данных.

### <a name="communication-compliance"></a>Соответствие требованиям к обмену данными

Для [проверки сторонних](communication-compliance.md) данных можно использовать соответствие требованиям связи, чтобы убедиться, что они соответствуют стандартам данных организации. Это можно сделать, обнаруживая, захватывая и принимая меры по исправлению неподобающих сообщений в организации. Например, вы можете отслеживать сторонние данные, импортируемые для оскорбительных языков, конфиденциальной информации и соответствия нормативным требованиям.

### <a name="insider-risk-management"></a>Управление внутренними рисками

Сигналы из сторонних данных, например выборочные данные по персоналу, могут использоваться решением по управлению рисками [insider](insider-risk-management.md) для минимизации внутренних рисков, позволяя обнаруживать, исследовать и действовать на рискованных действиях в вашей организации. Например, данные, импортируемые соединитетелем данных hr, используются в качестве индикаторов риска для обнаружения убывающих краж данных сотрудников.

## <a name="data-connectors-in-the-us-government-cloud"></a>Соединители данных в облаке правительства США

Как уже упоминалось ранее, соединители данных, предоставляемые TeleMessage, доступны в облаке правительства США. В следующей таблице указаны конкретные правительственные среды, поддерживают каждый соединитатель данных TeleMessage. Дополнительные сведения о облаках правительства США см. в Microsoft 365 [правительства США.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)

|Соединители данных TeleMessage  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Архивер Android | Да | Нет | Нет |
|Архив&T SMS/MMS Network Archiver | Да | Нет | Нет |
|Архивер сети Bell SMS/MMS | Да | Нет | Нет |
|Enterprise Архивер номеров | Да | Нет | Нет |
|Архивер SMS и голосовой сети O2 | Да         | Нет | Нет |
|Архивер SMS-сети TELUS | Да | Нет | Нет |
|Сетевой архивер Verizon SMS/MMS | Да | Нет | Нет |
|Архивер WeChat | Да | Нет | Нет |
|Архивер WhatsApp | Да | Нет | Нет |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Работа с партнером Майкрософт для архива сторонних данных

Другим вариантом импорта и архива сторонних данных является работа вашей организации с партнером Майкрософт. Если сторонний тип данных не поддерживается соединиттелями данных, доступными в центре соответствия требованиям Майкрософт, вы можете работать с партнером, который может предоставить настраиваемый соединититель, настроенный для регулярного извлечения элементов из стороннего источника данных, а затем подключения к облаку Майкрософт сторонним API и импорта этих элементов в Microsoft 365. Соединититель партнеров также преобразует содержимое элемента из источника сторонних данных в сообщение электронной почты, а затем импортирует его в почтовый ящик в Microsoft 365.

Список партнеров, с которые можно работать, и пошаговая процедура для этого метода см. в статью Работа с партнером для архивации сторонних данных в [Microsoft 365](work-with-partner-to-archive-third-party-data.md).
