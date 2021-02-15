---
title: План окончания поддержки Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Поддержка Project Server 2010 заканчивается 13 апреля 2021 г. Используйте эту статью в качестве руководства по обновлению до Project Online или более новой версии Project Server в локальной версии.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519706"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2010

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Поддержка Project Server 2010 завершится **13 апреля 2021 г.** Эта дата была расширена с предыдущей даты окончания поддержки 13 октября 2020 г. Если вы в настоящее время используете Project Server 2010, обратите внимание, что эти связанные продукты имеют следующие даты окончания поддержки:

|Продукт |Дата окончания поддержки|
|---|---|
|Project 2010 Standard|13 октября 2020 г.|
|Project 2010 Professional|13 октября 2020 г.|

Дополнительные сведения об окончании поддержки см. в обновлении с серверов [Office 2010 и клиентских продуктов.](plan-upgrade-previous-versions-office.md)

## <a name="what-does-end-of-support-mean"></a>Что означает *окончание поддержки?*

Почти все продукты Майкрософт имеют жизненный цикл поддержки, в течение которого они получают новые функции, исправления ошибок и обновления для системы безопасности. Этот жизненный цикл обычно длится 10 лет с начального выпуска продукта. Завершение этого жизненного цикла называется завершением поддержки продукта. После того как 13 апреля 2020 г. поддержка Project Server 2010 завершится, корпорация Майкрософт перестает предоставлять:

- Техническая поддержка для проблем, которые могут возникнуть.

- Исправления ошибок, обнаруженных и которые могут повлиять на стабильность и доступность сервера.

- Исправления для обнаруженных уязвимостей, которые могут сделать сервер уязвимым к нарушению безопасности.

- Обновления часовой пояс.

Установка Project Server 2010 продолжится после этой даты. Однако из-за изменений, перечисленных выше, настоятельно рекомендуется как можно скорее перейти с Project Server 2010.

## <a name="what-are-my-options"></a>Какие у меня есть варианты?

Возможные варианты миграции:

- Переход на Project Online

- Переход на более новую версию Project Server (предпочтительно Project Server 2019)

Вот два пути, которые можно использовать, чтобы избежать окончания поддержки Project Server 2010.

![Пути обновления Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Почему я хочу перейти на Project Server 2019?|Почему я хочу перейти на Project Online?|
|---|---|
|Бизнес-правила ограничивают работу моей компании в облаке.  <br/><br/>  Мне нужно управлять обновлениями в своей среде.|У меня есть мобильные или удаленные пользователи.<br/><br/>  Стоимость переноса на локальном сервере является серьезной проблемой (оборудование, программное обеспечение, время и усилия для реализации и так далее). <br/><br/>  После миграции затраты на обслуживание среды являются проблемой (например, автоматические обновления, гарантированное время работы и так далее).|

> [!NOTE]
> Дополнительные сведения о вариантах миграции см. в справке "Ресурсы по обновлению с серверов и клиентов [Office 2010".](upgrade-from-office-2010-servers-and-products.md) Обратите внимание, что Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут совместно использовать один пул ресурсов.

### <a name="what-are-my-options-for-project-client"></a>Какие у меня есть варианты для клиента Project?

Если вы используете Project профессиональный 2010 или Project Стандартный 2010, возможные варианты:

- Переход на более новую версию Project профессиональный или Project Стандартный
- Переход к сетевому решению, такому как Project Online или Project в Интернете

#### <a name="move-to-a-newer-version-of-project-client"></a>Переход на более новую версию клиента Project

При переходе с Project Стандартный 2010 можно перейти на более новую версию Project Standard (Project Стандартный 2016 или Project Стандартный 2019). Рекомендуем перейти к последней версии, чтобы воспользоваться новейшими возможностями. Миграция на менее текущую версию (Project Стандартный 2016) также означает, что вам потребуется перейти еще раз раньше.

Аналогично, при переходе с Project профессиональный 2010 можно перейти на более новую версию (Project профессиональный 2019 или Project профессиональный 2016). По возможности переходить к новой версии. Если для подключения к Project Server используется Project профессиональный, необходимо перейти на версию Project профессиональный, которая подключается к используемой версии Project Server.

Пользователи Project профессиональный 2010 также могут перейти на настольный клиент Project Online, который является версией Project профессиональный 2019 на основе подписки. Она включена в подписки project Plan 3 и Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Переход к сетевому решению

Вы также можете перейти с Project профессиональный 2010 или Project Стандартный 2010 на веб-решение на основе подписки Project. И Project ( план 3, и план 5) включают Project Online и последнее облачное предложение [Project для Интернета.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Обе функции предоставляют новые возможности и преимущества, которые стоит изучить.

Дополнительные сведения о функциях и лицензиях см. в [описании службы Microsoft Project.](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Важные аспекты переноса из Project Server 2010

При планировании миграции с Project Server 2010 учитывайте следующее:

- **Получите помощь от поставщика решений Майкрософт.** Обновление Project Server 2010 может быть сложной задачей. Для этого требуется большая подготовка и планирование. Это может быть особенно сложно, если вы не были человеком, который изначально установил Project Server 2010. Поставщики решений Майкрософт могут помочь при планировании перехода на Project Server 2019 или Project Online. Поиск поставщика решений в [Центре поставщиков решений Майкрософт.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Планирование настроек.** Настройки в среде Project Server 2010 могут не работать при переходе на Project Server 2019 или Project Online. В архитектуре Project Server существуют значительные различия между версиями. Кроме того, необходимые операционные системы, серверы баз данных и веб-браузеры, работающие с версиями, отличаются. Запланируйте тестирование или перестроение настроек в новой среде. Эта возможность дает возможность определить, нужны ли по-прежнему определенные настройки. Дополнительные сведения см. в сведениях о создании плана текущих настроек во время [обновления до SharePoint 2013.](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)

- **Время и терпение.** Планирование, выполнение и тестирование обновлений займет много времени и усилий, особенно при обновлении до Project Server 2019. При переходе с Project Server 2010 на Project Server 2019 необходимо сначала перейти на Project Server 2013, проверить данные, а затем перейти на Project Server 2016, а затем на Project Server 2019. Вам может потребоваться уточнить у поставщика решений Майкрософт время и предполагаемые затраты на помощь.

## <a name="migrate-to-project-online"></a>Переход на Project Online

Если вы решили перейти с Project Server 2010 на Project Online, выполните следующие действия, чтобы вручную перенести данные плана проекта:

1. Сохраните планы проектов из Project Server 2010 в формат MPP.

2. Используя Project профессиональный 2016, Project профессиональный 2019 или клиент Project Online для настольных ПК, откройте каждый MPP-файл, а затем сохраните и опубликуем его в Project Online.

Вы можете вручную создать конфигурацию PWA в Project Online (например, воссоздать все необходимые настраиваемые поля или корпоративные календари). Поставщики решений Майкрософт также могут помочь в этом процессе.

Ключевые ресурсы:

|Ресурс|Описание|
|---|---|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Настройка и использование Project Online|
|[Описание службы Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Сведения о различных доступных планах Project Online|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Переход на более новую версию Project Server в локальной версии

Мы настоятельно верим, что переход на Project Online будет наиболее удобным и удобным для пользователя. Но мы также понимаем, что некоторым организациям необходимо хранить данные проекта в локальной организации. Если вы решили хранить данные проекта локально, можно перенести среду Project Server 2010 в Project Server 2013, Project Server 2016 или Project Server 2019.

Если вы не можете перейти на Project Online, рекомендуется перейти на Project Server 2019. Project Server 2019 включает большинство ключевых функций в предыдущих выпусках Project Server. И он наиболее точно соответствует возможностям Project Online, хотя некоторые функции доступны только в Project Online.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

> [!NOTE]
> Если вы ограничены только локальной версией решения и рассматриваете возможность перехода только на Project Server 2013, следует учитывать, что этой версии осталось всего несколько лет поддержки. Дата окончания поддержки Project Server 2013 с 2 Пакет обновления 13 октября 2023 г. Дополнительные сведения о датах окончания поддержки см. в политике [жизненного цикла продуктов Майкрософт.](https://go.microsoft.com/fwlink/p/?linkid=842066)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Как перейти на Project Server 2019?

Архитектурные различия между Project Server 2010 и Project Server 2019 препятствуют прямому пути миграции. Таким образом, вам потребуется перенести данные Project Server 2010 на каждую из последовательных версий Project Server, пока не достигнете Project Server 2019. Действия по обновлению Project Server 2010 до Project Server 2019:

1. Миграция на Project Server 2013.

2. Миграция с Project Serve 2013 на Project Server 2016.

3. Миграция с Project Server 2016 на Project Server 2019.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

### <a name="step-1-migrate-to-project-server-2013"></a>Шаг 1. Миграция на Project Server 2013

Подробную информацию об обновлении Project Server 2010 до Project Server 2013 см. в обновлении до [Project Server 2013.](https://go.microsoft.com/fwlink/p/?linkid=841822)

Ключевые ресурсы:

- [Обзор этапов обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Общие сведения об обновлении Project Server 2010 до Project Server 2013.
- [Планирование обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  В этой теме рассматриваются вопросы планирования при обновлении Project Server 2010 до Project Server 2013, включая требования к системе.

- [Новые возможности обновления Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) охватывают важные изменения в этой версии, в том числе:

   - Обновление на месте до Project Server 2013 не происходит. Метод с перенастройки баз данных — единственный поддерживаемый способ обновления с Project Server 2010 до Project Server 2013.

   - Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но и объединяет четыре базы данных Project Server 2010 в одну Project Web App данных.

   - В SharePoint Server 2013 и Project Server 2013 проверка подлинности на основе утверждений была изменена по сравнению с предыдущей версией. Если вы используете классическую проверку подлинности, это необходимо учитывать при обновлении. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Ключевые ресурсы:

- [Общие сведения о процессе обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Схема процесса обновления Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Большая консолидация баз данных, перенос Project Server 2010 на 2013 за 8 простых шагов](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Шаг 2. Миграция на Project Server 2016

После перехода на Project Server 2013 и проверки успешного переноса данных необходимо перейти на Project Server 2016.

Дополнительные сведения см. в [обновлении до Project Server 2016.](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор процесса обновления до Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Понять, что необходимо сделать для обновления Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  В этой теме рассматриваются вопросы планирования при обновлении Project Server 2013 до Project Server 2016.

Что нужно знать об обновлении [Project Server 2016,](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) относятся важные изменения при обновлении до этой версии, в том числе:

- При создании среды Project Server 2016 обратите внимание, что файлы установки Project Server 2016 включены в SharePoint Server 2016. Дополнительные сведения [см. в подпроекте "Развертывание Project Server 2016".](https://go.microsoft.com/fwlink/p/?linkid=841829)

- Планы использования ресурсов в Project Server 2016 являются неподготовленными. Планы использования ресурсов Project Server 2013 будут перенесены в project Server 2016 и Project Online. Дополнительные [сведения см. в обзоре.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870)

### <a name="step-3-migrate-to-project-server-2019"></a>Шаг 3. Миграция на Project Server 2019

После миграции в Project Server 2016 и проверки успешного переноса данных необходимо перенести данные в Project Server 2019.

Чтобы узнать, что нужно сделать для обновления Project Server 2016 до Project Server 2019, см. обновление [до Project Server 2019.](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор процесса обновления Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Получите общее представление о том, что необходимо сделать для обновления Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  В этой теме рассматриваются вопросы планирования обновления Project Server 2016 до Project Server 2019.

- [Что нужно знать об обновлении Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Узнайте о важных изменениях при обновлении до этой версии, в том числе:

   - Процесс обновления переносит данные из базы данных Project Server 2016 в базу данных контента SharePoint Server 2019.  Project Server 2019 больше не будет создавать собственную базу данных Project Server в ферме SharePoint Server.

   - После обновления следует помнить о нескольких изменениях в Project Web App.  Подробные сведения см. в новых [сведениях в Project Server 2019.](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Другие ресурсы:**

- [Описание службы Project Online:](https://go.microsoft.com/fwlink/p/?linkid=841280)см. функции управления портфелями, включенные в Project Server 2016 и Project Online premium.

- [Microsoft Office переноса Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Сводка параметров для клиентов и серверов Office 2010 и Windows 7

Визуальное представление возможностей обновления, миграции и перехода на облачные решения для клиентов и серверов Office 2010, а также Windows 7 см. на плакате [Прекращение поддержки](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Окончание поддержки клиентов и серверов Office 2010 и плаката windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

На этом плакате показано, как обойтись без поддержки клиентских и серверных продуктов Office 2010 и Windows 7. Выделены предпочтительные пути и поддержка вариантов в Microsoft 365 корпоративный.

Вы также можете [скачать](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) этот плакат и распечатать его в формате букв, юридических или таблоидов (11 x 17).

## <a name="related-topics"></a>Связанные статьи

[Переход с SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Обновление серверов и клиентов Office 2010](upgrade-from-office-2010-servers-and-products.md)
