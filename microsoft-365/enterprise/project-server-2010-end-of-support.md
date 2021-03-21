---
title: Дорожная карта project Server 2010 на конец поддержки
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
description: Заканчивается поддержка Project Server 2010 13 апреля 2021 г. Используйте эту статью в качестве руководства для обновления до Project Online или более новой версии локального project Server.
ms.openlocfilehash: 807c09bff0cb6331b872474acc22f8d2c622a6c6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927376"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2010

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Project Server 2010 завершит поддержку **13 апреля 2021 г.** Эта дата была продлена с предыдущей даты окончания поддержки 13 октября 2020 г. Если вы в настоящее время используете Project Server 2010, обратите внимание, что эти связанные продукты имеют следующие даты окончания поддержки:

|Продукт |Конец даты поддержки|
|---|---|
|Стандарт project 2010|13 октября 2020 г.|
|Project 2010 Professional|13 октября 2020 г.|

Дополнительные сведения о достижении конца поддержки см. в [веб-сведениях Upgrade from Office 2010 servers and client products.](plan-upgrade-previous-versions-office.md)

## <a name="what-does-end-of-support-mean"></a>Что означает *конец поддержки?*

Почти все продукты Майкрософт имеют жизненный цикл поддержки, в ходе которого они получают новые функции, исправления ошибок и обновления безопасности. Этот жизненный цикл обычно длится 10 лет с начального выпуска продукта. Конец жизненного цикла называется завершением поддержки продукта. После окончания поддержки Project Server 2010 13 апреля 2021 г. Корпорация Майкрософт больше не будет предоставлять:

- Техническая поддержка проблем, которые могут возникнуть.

- Исправление ошибок для обнаруженных проблем, которые могут повлиять на стабильность и доступность сервера.

- Исправления безопасности для обнаруженных уязвимостей, которые могут сделать сервер уязвимым для нарушений безопасности.

- Обновления часовой зоны.

Установка Project Server 2010 продолжится после этой даты. Но из-за изменений, перечисленных ранее, настоятельно рекомендуется как можно скорее перейти с Project Server 2010.

## <a name="what-are-my-options"></a>Какие у меня варианты?

Параметры миграции:

- Миграция в Project Online

- Миграция в более новую локальной версии Project Server (предпочтительно Project Server 2019)

Вот два пути, которые можно использовать, чтобы избежать окончания поддержки Project Server 2010.

![Пути обновления Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Почему я предпочитаю перейти на Project Server 2019?|Почему я предпочитаю перейти в Project Online?|
|---|---|
|Бизнес-правила ограничивают работу бизнеса в облаке.  <br/><br/>  Мне нужен контроль над обновлениями в своей среде.|У меня есть мобильные или удаленные пользователи.<br/><br/>  Значительные затраты на перенос локального сервера (оборудование, программное обеспечение, время и усилия для реализации и так далее). <br/><br/>  После переноса вызывает озабоченность затраты на поддержание среды (например, автоматические обновления, гарантированное время простоя и так далее).|

> [!NOTE]
> Дополнительные сведения о параметрах миграции см. в справке Ресурсы, которые помогут вам обновить [серверы и клиенты Office 2010.](upgrade-from-office-2010-servers-and-products.md) Обратите внимание, что Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут использовать один и тот же пул ресурсов.

### <a name="what-are-my-options-for-project-client"></a>Каковы мои параметры для клиента Project?

Если вы используете Project Professional 2010 или Project Standard 2010, вы можете использовать:

- Переход на более новую версию Project Professional или Project Standard
- Переход к решению в Интернете, например Project Online или Project for the web

#### <a name="move-to-a-newer-version-of-project-client"></a>Переход на более новую версию клиента Project

При переходе из Project Standard 2010 можно перейти к более новой версии Project Standard (Project Standard 2016 или Project Standard 2019). Рекомендуется перейти в новейшую версию, чтобы воспользоваться последними функциями. Миграция в менее текущую версию (Project Standard 2016) также означает, что вам потребуется перенести еще раз раньше.

Кроме того, при переходе из Project Professional 2010 можно перейти на более новую версию (Project Professional 2019 или Project Professional 2016). Снова переходить к самой новой версии, если это возможно. Если вы используете Project Professional для подключения к Project Server, убедитесь, что вы мигрируете в версию Project Professional, которая подключается к используемой версии Project Server.

Пользователи Project Professional 2010 также могут перейти на клиент Project Online Desktop, который является версией Project Professional 2019 на основе подписки. Он включен в подписки Project Plan 3 и Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Переход к решению в Интернете

Вы также можете перейти из Project Professional 2010 или Project Standard 2010 в сетевое решение на основе подписки Project. И Project Plan 3, и Plan 5 включают Project Online и последнее облачное предложение [Project for the Web.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Оба предлагают новые возможности и преимущества, которые стоит изучить.

Дополнительные сведения об особенностях и лицензиях см. в описании [службы Microsoft Project.](/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Важные соображения для переноса с Project Server 2010

При планировании миграции с Project Server 2010 рассмотрим следующее:

- **Получить помощь от поставщика решений Майкрософт** . Обновление с Project Server 2010 может быть сложной задачей. Это требует большой подготовки и планирования. Это может быть особенно сложно, если вы не были человеком, который изначально создал Project Server 2010. Поставщики решений Майкрософт могут помочь независимо от того, планируете ли вы перейти на Project Server 2019 или Project Online. Поиск поставщика решений в [центре поставщиков решений Майкрософт.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Планирование настроек** . Настройки в среде Project Server 2010 могут не работать при переходе на Project Server 2019 или Project Online. В архитектуре Project Server существуют значительные различия между версиями. Кроме того, различаются необходимые операционные системы, серверы баз данных и веб-браузеры, работающие с версиями. У вас есть план тестирования или восстановления настроек в новой среде. Воспользоваться этой возможностью, чтобы определить, необходимы ли определенные настройки. Дополнительные сведения см. в раздел Создание плана текущих настроек во время обновления [до SharePoint 2013.](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)

- **Время и терпение** . Планирование обновления, выполнение и тестирование будут отбирать много времени и усилий, особенно для обновления до Project Server 2019. Если вы мигрируете с Project Server 2010 на Project Server 2019, сначала необходимо перейти на Project Server 2013, проверить данные, а затем перейти на Project Server 2016, а затем на Project Server 2019. Возможно, вам нужно проверить у поставщика решений Майкрософт сроки и предполагаемые затраты для их оказания помощи.

## <a name="migrate-to-project-online"></a>Миграция в Project Online

Если вы решите перейти с Project Server 2010 на Project Online, вы можете выполнять следующие действия для переноса данных плана проекта вручную:

1. Сохраните планы проекта с Project Server 2010 до формата MPP.

2. С помощью Project Professional 2016, Project Professional 2019 или Клиент настольного компьютера Project Online откройте каждый файл MPP, а затем сохраните и опубликуем его в Project Online.

Вы можете вручную создать конфигурацию PWA в Project Online (например, воссоздать необходимые настраиваемые поля или корпоративные календари). Поставщики решений Майкрософт также могут помочь в этом процессе.

Ключевые ресурсы:

|Resource|Описание|
|---|---|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Настройка и использование Project Online|
|[Описание службы Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Сведения о различных доступных планах Project Online|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Миграция в более новую локальной версию Project Server

Мы твердо верим, что вы получите лучшее значение и пользовательский опыт, переехав в Project Online. Но мы также понимаем, что некоторым организациям необходимо хранить данные о проектах на месте. Если вы хотите сохранить данные проекта на локальной основе, вы можете перенести среду Project Server 2010 в Project Server 2013, Project Server 2016 или Project Server 2019.

Если вы не можете перейти в Project Online, рекомендуется перейти на Project Server 2019. Project Server 2019 включает большинство ключевых функций в предыдущих выпусках Project Server. И это наиболее тесно совпадает с опытом, доступным в Project Online, хотя некоторые функции доступны только в Project Online.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

> [!NOTE]
> Если вы ограничиваете локальное решение и рассматриваете только переход на Project Server 2013, будьте осторожны, что эта версия имеет еще несколько лет поддержки. Дата окончания даты поддержки Project Server 2013 с Пакет обновления 13 октября 2023 г. Дополнительные сведения о сроках окончания службы поддержки см. в сайте [Microsoft Product Lifecycle Policy.](/lifecycle/)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Как перейти на Project Server 2019?

Архитектурные различия между Project Server 2010 и Project Server 2019 препятствуют прямой миграции. Поэтому вам потребуется перенести данные Project Server 2010 в каждую сеяную версию Project Server до достижения Project Server 2019. Действия по обновлению Project Server 2010 до Project Server 2019:

1. Миграция на Project Server 2013.

2. Перенос с Project Serve 2013 на Project Server 2016.

3. Перенос с Project Server 2016 на Project Server 2019.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

### <a name="step-1-migrate-to-project-server-2013"></a>Шаг 1. Миграция на Project Server 2013

Подробную информацию о обновлении с Project Server 2010 до Project Server 2013 см. в обзоре [Upgrade to Project Server 2013.](/project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор этапов обновления до Project Server 2013](/project/upgrade-to-project-server-2016)

  Получите краткий обзор обновления с Project Server 2010 до Project Server 2013.
- [План обновления до Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Посмотрите на соображения планирования при обновлении с Project Server 2010 до Project Server 2013, включая требования к системе.

- [Новые возможности обновления Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) охватывают важные изменения для этой версии, в том числе:

   - Обновление до Project Server 2013 не происходит на месте. Метод прикрепить базу данных — это единственный поддерживаемый способ обновления с Project Server 2010 до Project Server 2013.

   - Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но и консолидирует четыре базы данных Project Server 2010 в одну Project Web App базу данных.

   - Как SharePoint Server 2013, так и Project Server 2013 изменены на проверку подлинности на основе утверждений из предыдущей версии. Если вы используете классическую проверку подлинности, это необходимо учитывать при обновлении. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Ключевые ресурсы:

- [Общие сведения о процессе обновления до Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)

- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Схема процесса обновления Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Большая консолидация баз данных, Project Server 2010 - 2013 Migration in 8 Easy Steps](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Шаг 2. Миграция на Project Server 2016

После перехода на Project Server 2013 и проверки успешного переноса данных на Project Server 2016 следующий шаг.

Дополнительные сведения см. в [веб-сведениях Upgrade to Project Server 2016.](/Project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор процесса обновления до Project Server 2016](/Project/overview-of-the-project-server-2016-upgrade-process)

  Понять, что нужно сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  При обновлении с Project Server 2013 до Project Server 2016 посмотрите на соображения планирования.

[Все, что необходимо знать о обновлении Project Server 2016,](/project/plan-for-upgrade-to-project-server-2016#thingknow) содержит важные изменения для обновления до этой версии, включающие:

- При создании среды Project Server 2016 обратите внимание, что файлы установки Project Server 2016 включены в SharePoint Server 2016. Дополнительные сведения см. в [веб-сведениях Deploy Project Server 2016.](/project/deploy-project-server-2016)

- В Project Server 2016 планы ресурсов не априорные. Планы ресурсов Project Server 2013 будут перенесены в Проекты Сервер 2016 и Project Online. Дополнительные сведения см. в [обзоре.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870)

### <a name="step-3-migrate-to-project-server-2019"></a>Шаг 3. Миграция на Project Server 2019

После перехода на Project Server 2016 и проверки успешной миграции данных следующим шагом является перенос данных на Project Server 2019.

Подробнее о том, что необходимо сделать для обновления с Project Server 2016 до Project Server 2019, см. в руб. Обновление до [Project Server 2019.](/Project/upgrade-to-project-server-2016)

Ключевые ресурсы:

- [Обзор процесса обновления Project Server 2019](/project/overview-of-the-project-server-2019-upgrade-process)

  Получите четкое представление о том, что необходимо сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  Подробнее о планировании обновления с Project Server 2016 до Project Server 2019.

- [Что нужно знать об обновлении Project Server 2019](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Узнайте о важных изменениях для обновления до этой версии, которые включают:

   - В процессе обновления данные будут перенесены из базы данных Project Server 2016 в базу данных контента SharePoint Server 2019.  Project Server 2019 больше не будет создавать собственную базу данных Project Server в ферме SharePoint Server.

   - После обновления следует помнить о нескольких изменениях в Project Web App.  Подробные сведения см. в материале [What's new in Project Server 2019.](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Другие ресурсы:**

- [Описание службы](/office365/servicedescriptions/project-online-service-description/project-online-service-description)Project Online: См. функции управления портфелем, включенные в Project Server 2016 и Project Online Premium.

- [Microsoft Office project Portfolio Server 2010 migration guide](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Сводка параметров для клиентов и серверов Office 2010 и Windows 7

Визуальное представление возможностей обновления, миграции и перехода на облачные решения для клиентов и серверов Office 2010, а также Windows 7 см. на плакате [Прекращение поддержки](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Завершение поддержки клиентов и серверов Office 2010 и плаката Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

На этом плакате показано, как избежать окончания поддержки клиентских и серверных продуктов Office 2010 и Windows 7 с предпочтительными путями и поддержкой опций в Microsoft 365 Enterprise.

Вы также можете [скачать](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) этот плакат и распечатать его в формате букв, юридических или таблоидов (11 x 17).

## <a name="related-topics"></a>Родственные темы

[Переход с SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Обновление серверов и клиентов Office 2010](upgrade-from-office-2010-servers-and-products.md)