---
title: Project Дорожная карта конца поддержки Server 2010
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
description: Заканчивается поддержка Project Server 2010 13 апреля 2021 г. Используйте эту статью в качестве руководства для обновления Project Online или более новой версии локальной Project Server.
ms.openlocfilehash: f57fa15da3cabc4b326a52359a29c652fcbe9e7f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842234"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2010

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Project Сервер 2010 достигнет конца поддержки **13 апреля 2021 .** Эта дата была продлена с предыдущей даты окончания поддержки 13 октября 2020 г. Если в настоящее время используется Project Server 2010, обратите внимание, что эти связанные продукты имеют следующие даты окончания поддержки:

|Продукт |Конец даты поддержки|
|---|---|
|Project 2010 standard|13 октября 2020 г.|
|Project 2010 Professional|13 октября 2020 г.|

Дополнительные сведения о достижении конца поддержки см. в Office [2010](plan-upgrade-previous-versions-office.md)серверов и клиентских продуктов.

## <a name="what-does-end-of-support-mean"></a>Что означает *конец поддержки?*

Почти все продукты Майкрософт имеют жизненный цикл поддержки, в ходе которого они получают новые функции, исправления ошибок и обновления безопасности. Этот жизненный цикл обычно длится 10 лет с начального выпуска продукта. Конец жизненного цикла называется завершением поддержки продукта. После Project 13 апреля 2021 г. корпорация Майкрософт больше не будет предоставлять:

- Техническая поддержка проблем, которые могут возникнуть.

- Исправление ошибок для обнаруженных проблем, которые могут повлиять на стабильность и доступность сервера.

- Исправления безопасности для обнаруженных уязвимостей, которые могут сделать сервер уязвимым для нарушений безопасности.

- Обновления часовой зоны.

Установка Project Server 2010 продолжится после этой даты. Но из-за изменений, перечисленных ранее, настоятельно рекомендуется как можно скорее перенести Project Server 2010.

## <a name="what-are-my-options"></a>Какие у меня варианты?

Параметры миграции:

- Миграция в Project Online

- Миграция в более новую локальной версии Project Server (предпочтительно Project Server 2019)

Вот два пути, которые можно использовать, чтобы избежать окончания поддержки Project Server 2010.

![Project Пути обновления Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Почему я предпочитаю перейти на Project Server 2019?|Почему я предпочитаю перейти на Project Online?|
|---|---|
|Бизнес-правила ограничивают работу бизнеса в облаке.  <br/><br/>  Мне нужен контроль над обновлениями в своей среде.|У меня есть мобильные или удаленные пользователи.<br/><br/>  Значительные затраты на перенос локального сервера (оборудование, программное обеспечение, время и усилия для реализации и так далее). <br/><br/>  После переноса вызывает озабоченность затраты на поддержание среды (например, автоматические обновления, гарантированное время простоя и так далее).|

> [!NOTE]
> Дополнительные сведения о параметрах миграции см. в справке Ресурсы, которые помогут вам обновиться с Office серверов и [клиентов 2010 г.](upgrade-from-office-2010-servers-and-products.md) Обратите внимание, Project Server не поддерживает гибридную конфигурацию, так как Project Сервер и Project Online не могут использовать один и тот же пул ресурсов.

### <a name="what-are-my-options-for-project-client"></a>Каковы мои параметры для Project клиента?

Если вы используете Project профессиональный 2010 или Project стандартный 2010 г., вы можете использовать:

- Переход на более новую версию Project профессиональный или Project стандартный
- Переходить к решению в Интернете, например Project Online или Project веб-сайте

#### <a name="move-to-a-newer-version-of-project-client"></a>Переход на более новую версию Project клиента

При переносе с Project стандартный 2010 г. можно перейти к более новой версии Project стандартный (Project стандартный 2016 или Project стандартный 2019 г.). Рекомендуется перейти в новейшую версию, чтобы воспользоваться последними функциями. Миграция в менее текущую версию (Project стандартный 2016) также означает, что вам потребуется перенести еще раз раньше.

Аналогичным образом, если вы Project профессиональный 2010 г., вы можете перейти к более новой версии (Project профессиональный 2019 или Project профессиональный 2016). Снова переходить к самой новой версии, если это возможно. Если вы Project профессиональный для подключения к Project Server, убедитесь, что вы мигрируете в версию Project профессиональный, которая подключается к версии Project Server, которую вы используете.

Project профессиональный 2010 года пользователи также могут перейти на клиент Project Online Desktop, который является подпиской версии Project профессиональный 2019. Он включен в Project, план 3 и Project, план 5 подписки.

#### <a name="move-to-an-online-solution"></a>Переход к решению в Интернете

Вы также можете перейти Project профессиональный 2010 или Project стандартный 2010 г. в Project на основе подписки в Интернете. И Project, план 3, и план 5 включают Project Online и последнее облачное предложение, [Project веб](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Оба предлагают новые возможности и преимущества, которые стоит изучить.

Дополнительные сведения об особенностях и лицензиях см. в Microsoft Project [описание службы.](/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Важные соображения для переноса Project Server 2010

При планировании миграции с Project Server 2010 рассмотрим следующее:

- **Получить помощь от поставщика решений Майкрософт** . Обновление Project Server 2010 может быть сложной задачей. Это требует большой подготовки и планирования. Это может быть особенно сложно, если вы не были человеком, который изначально Project Server 2010. Поставщики решений Майкрософт могут помочь, планируете ли вы перейти на Project Server 2019 или Project Online. Поиск поставщика решений в [центре поставщиков решений Майкрософт.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Планирование настроек** . Настройки в среде Project Server 2010 могут не работать при миграции на Project Server 2019 или Project Online. Существуют значительные различия в архитектуре Project Server между версиями. Кроме того, различаются необходимые операционные системы, серверы баз данных и веб-браузеры, работающие с версиями. У вас есть план тестирования или восстановления настроек в новой среде. Воспользоваться этой возможностью, чтобы определить, необходимы ли определенные настройки. Дополнительные сведения см. в рублях Создание плана текущих настроек во время обновления [SharePoint 2013 г.](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)

- **Время и терпение** . Планирование обновления, выполнение и тестирование займет много времени и усилий, особенно для обновления до Project Server 2019. Если вы мигрируете с Project Server 2010 на Project Server 2019, сначала необходимо перейти на Project Server 2013, проверить данные, а затем перейти на Project Server 2016, а затем на Project Server 2019. Возможно, вам нужно проверить у поставщика решений Майкрософт сроки и предполагаемые затраты для их оказания помощи.

## <a name="migrate-to-project-online"></a>Миграция в Project Online

Если вы решите перейти с Project Server 2010 на Project Online, вы можете следовать этим шагам, чтобы вручную перенести данные плана проекта:

1. Сохраните планы проекта с Project Server 2010 до формата MPP.

2. Используя Project профессиональный 2016, Project профессиональный 2019 г. или Project Online desktop Client, откройте каждый файл MPP, а затем сохраните и опубликуите его в Project Online.

Вы можете вручную создать конфигурацию PWA в Project Online (например, воссоздать необходимые настраиваемые поля или корпоративные календари). Поставщики решений Майкрософт также могут помочь в этом процессе.

Ключевые ресурсы:

|Ресурс|Описание|
|---|---|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Настройка и использование Project Online|
|[Описание службы Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Сведения о различных планах Project Online доступных|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Перенос в более новую локальной версии Project Server

Мы твердо верим, что вы получите лучшее значение и пользовательский опыт, переехав в Project Online. Но мы также понимаем, что некоторым организациям необходимо хранить данные о проектах на месте. Если вы решите хранить данные проекта на локальной основе, вы можете перенести среду Project Server 2010 в Project Server 2013, Project Server 2016 или Project Server 2019.

Если вы не можете перейти в Project Online, рекомендуем перейти на Project Server 2019. Project Сервер 2019 включает большинство ключевых функций в предыдущих выпусках Project Server. И это наиболее тесно совпадает с опытом, доступным с Project Online, хотя некоторые функции доступны только в Project Online.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

> [!NOTE]
> Если вы ограничиваете локальное решение и рассматриваете только переход на Project Server 2013, будьте осторожны, что эта версия имеет еще несколько лет поддержки. Окончание даты поддержки Project Server 2013 с Пакет обновления 13 октября 2023 г. Дополнительные сведения о сроках окончания службы поддержки см. в сайте [Microsoft Product Lifecycle Policy.](/lifecycle/)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Как перейти на Project Server 2019?

Архитектурные различия между Project Server 2010 и Project Server 2019 препятствуют прямой миграции. Поэтому вам потребуется перенести данные Project Server 2010 в каждую последовательный вариант Project Server, пока не достигнете Project Server 2019. Действия по обновлению Project Server 2010 до Project Server 2019:

1. Миграция на Project Server 2013.

2. Миграция из Project Serve 2013 в Project Server 2016.

3. Перенос с Project Server 2016 на Project Server 2019.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

### <a name="step-1-migrate-to-project-server-2013"></a>Шаг 1. Миграция на Project Server 2013

Всеобъемлющую информацию об обновлении с Project Server 2010 до Project Server 2013 см. в Project [Server 2013.](/project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор этапов обновления до Project Server 2013](/project/upgrade-to-project-server-2016)

  Получите краткий обзор обновления с Project Server 2010 до Project Server 2013.
- [План обновления до Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Посмотрите на соображения планирования при обновлении Project Server 2010 до Project Server 2013, включая требования к системе.

- [Новое обновление Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) включает важные изменения для этой версии, в том числе:

   - Обновление на месте до Project Server 2013 не происходит. Метод прикрепить базу данных — это единственный поддерживаемый способ обновления с Project Server 2010 до Project Server 2013.

   - Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но и консолидирует четыре базы данных Project Server 2010 в одну базу данных Project Web App.

   - Как SharePoint Server 2013, так и Project Server 2013 изменены на проверку подлинности на основе утверждений из предыдущей версии. Если вы используете классическую проверку подлинности, это необходимо учитывать при обновлении. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( /sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Ключевые ресурсы:

- [Общие сведения о процессе обновления до Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Схема процесса обновления сервера](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Большая консолидация баз данных, Project Server 2010 до 2013 Миграция в 8 простых шагах](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Шаг 2. Миграция на Project Server 2016

После перехода на Project Server 2013 и проверки успешной миграции данных, следующий шаг — миграция в Project Server 2016.

Дополнительные сведения см. в [Project Server 2016.](/Project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор процесса обновления до Project Server 2016](/Project/overview-of-the-project-server-2016-upgrade-process)

  Понять, что нужно сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  При обновлении с Project Server 2013 до Project Server 2016.

[Все, что необходимо](/project/plan-for-upgrade-to-project-server-2016#thingknow) знать о Project Server 2016 обновления, включает важные изменения для обновления до этой версии, включающие:

- При создании Project Server 2016 среды обратите внимание, что Project Server 2016 файлы установки включены в SharePoint Server 2016. Дополнительные сведения см. в [Project Server 2016.](/project/deploy-project-server-2016)

- Планы ресурсов в Project Server 2016. Планы ресурсов Project Server 2013 будут перенесены в Project Server 2016 и Project Online. Дополнительные сведения см. в [обзоре.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870)

### <a name="step-3-migrate-to-project-server-2019"></a>Шаг 3. Миграция на Project Server 2019

После переноса в Project Server 2016 и проверки успешного переноса данных на сервер Server 2019 необходимо перенести их на Project Server 2019.

Чтобы узнать, что нужно сделать для обновления с Project Server 2016 до Project Server 2019, см. в Project [Server 2019.](/Project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор процесса обновления Project Server 2019](/project/overview-of-the-project-server-2019-upgrade-process)

  Получите четкое представление о том, что необходимо сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Посмотрите на соображения планирования обновления с Project Server 2016 до Project Server 2019.

- [Что нужно знать об обновлении Project Server 2019](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Узнайте о важных изменениях для обновления до этой версии, которые включают:

   - Процесс обновления будет мигрировать данные из Project Server 2016 базы данных в SharePoint Server 2019 контента.  Project Server 2019 больше не будет создавать собственную базу данных Project Server в ферме SharePoint Server.

   - После обновления следует помнить о нескольких изменениях в Project Web App.  Подробные сведения см. в материале [What's new in Project Server 2019.](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Другие ресурсы:**

- [Project Online service Descriptions](/office365/servicedescriptions/project-online-service-description/project-online-service-description): См. функции управления портфелями, включенные в Project Server 2016 и Project Online расширенный.

- [Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Сводка параметров для Office и серверов 2010 года и Windows 7

Визуальное представление возможностей обновления, миграции и перехода на облачные решения для клиентов и серверов Office 2010, а также Windows 7 см. на плакате [Прекращение поддержки](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Завершение поддержки клиентов и Office 2010 г. и Windows 7 плакатов](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

На этом плакате показано, как избежать окончания поддержки клиентских и серверных продуктов 2010 Office 2010 г. и Windows 7 с предпочтительными путями и поддержкой вариантов в Microsoft 365 корпоративный выделены.

Вы также можете [скачать](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) этот плакат и распечатать его в формате букв, юридических или таблоидов (11 x 17).

## <a name="related-topics"></a>Статьи по теме

[Переход с SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Обновление серверов и клиентов Office 2010](upgrade-from-office-2010-servers-and-products.md)