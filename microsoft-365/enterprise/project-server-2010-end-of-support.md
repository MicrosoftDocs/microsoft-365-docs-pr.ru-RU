---
title: План конечной поддержки Project Server 2010
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
description: Прекращение поддержки для Project Server 2010 завершается 13 апреля 2021. Используйте эту статью в качестве руководства по обновлению до Project Online или более новой версии Project Server в локальной среде.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519706"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2010

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Project Server 2010 дойдет до конца поддержки от **13 апреля 2021 г**. Эта дата была расширена с момента предыдущего срока поддержки 13 октября 2020 г. Если вы используете Project Server 2010, обратите внимание на то, что эти связанные продукты имеют следующие даты окончания поддержки:

|Продукт |Дата окончания поддержки|
|---|---|
|Project 2010 Стандартный|13 октября 2020 г.|
|Project 2010 профессиональный|13 октября 2020 г.|

Дополнительные сведения о достижении конца поддержки можно найти [в статье обновление с серверов и клиентских продуктов Office 2010](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>Что означает *Окончание поддержки* ?

Практически все продукты корпорации Майкрософт имеют жизненный цикл поддержки, в течение которого они получают новые функции, исправления ошибок и обновления для системы безопасности. Этот жизненный цикл обычно длится через 10 лет от первоначального выпуска продукта. Окончание этого жизненного цикла называется окончанием поддержки продукта. После того как Project Server 2010 достиг конца поддержки 13 апреля 2021, корпорация Майкрософт больше не будет предоставлять следующее:

- Техническая поддержка проблем, которые могут возникнуть.

- Исправление ошибок для обнаруженных проблем, которые могут повлиять на стабильность и удобство использования сервера.

- Исправления для системы безопасности уязвимостей, которые могут привести к уязвимости сервера при нарушении безопасности.

- Обновления часового пояса.

Установка Project Server 2010 продолжит работу после этой даты. Однако из-за перечисленных выше изменений настоятельно рекомендуется выполнить миграцию из Project Server 2010 как можно скорее.

## <a name="what-are-my-options"></a>Что такое параметры?

Возможные варианты миграции:

- Миграция в Project Online

- Переход на более новую локальную версию Project Server (желательно Project Server 2019)

Ниже приведены два пути, которые можно использовать, чтобы избежать завершения поддержки Project Server 2010.

![Пути обновления Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Зачем переходить на Project Server 2019?|Зачем нужна миграция в Project Online?|
|---|---|
|Бизнес-правила ограничивают меня рабочими моими предприятиями в облаке.  <br/><br/>  Мне нужно управлять обновлениями в моей среде.|У меня есть мобильные или удаленные пользователи.<br/><br/>  Затраты на миграцию локальных серверов очень важны (оборудование, программное обеспечение, время и усилия для реализации и т. д.). <br/><br/>  После миграции затраты на поддержание среды — это проблема (например, автоматическое обновление, Гарантированная работоспособность и т. д.).|

> [!NOTE]
> Для получения дополнительных сведений о параметрах миграции ознакомьтесь [со статьей ресурсы, которые помогут вам выполнить обновление серверов и клиентов Office 2010](upgrade-from-office-2010-servers-and-products.md). Обратите внимание, что Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут совместно использовать один пул ресурсов.

### <a name="what-are-my-options-for-project-client"></a>Что такое параметры для клиента Project?

Если вы используете Project профессиональный 2010 или Project стандартный 2010, доступны следующие варианты:

- Переход на новую версию Project профессиональный или Project Стандартный
- Переход к сетевому решению, такому как Project Online или Project для веба

#### <a name="move-to-a-newer-version-of-project-client"></a>Переход на новую версию клиента Project

Если вы выполняете миграцию из Project стандартный 2010, вы можете перейти к новой версии Project Standard (Project Стандартный 2016 или Project Стандартный 2019). Мы рекомендуем перейти к последней версии, чтобы воспользоваться преимуществами новейших функций. Переход на более новую версию (Project Стандартный 2016) также означает, что вам потребуется еще раз выполнить миграцию.

Аналогично, при переходе с Project профессиональный 2010 вы можете перейти к новой версии (Project профессиональный 2019 или Project профессиональный 2016). Опять же, перейдите к последней версии, если это возможно. Если вы используете Project профессиональный для подключения к Project Server, убедитесь, что вы переносите их в версию Project Professional, которая подключается к используемой версии Project Server.

Пользователи Project профессиональный 2010 также могут переходить на клиент Project Online для настольных ПК, который является версией Project профессиональный 2019 на основе подписки. Она включена в план подписки на проект 3 и проект план 5.

#### <a name="move-to-an-online-solution"></a>Переход к сетевому решению

Вы также можете выполнить миграцию из Project профессиональный 2010 или Project Standard 2010 в интерактивное решение на основе подписки на проект. В планах Project (план 3) и план 5 входит Project Online и Последнее облачное предложение, [Project для Интернета](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Оба предоставляют новые возможности и преимущества, которые стоит рассмотреть.

Для получения дополнительных сведений о функциях и лицензиях обратитесь к разделу [Описание службы Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Важные рекомендации по переходу с Project Server 2010

При планировании миграции из Project Server 2010 учитывайте следующее:

- **Получение справки от поставщика решений Майкрософт** : обновление с Project Server 2010 может быть непростой задачей. Для этого необходима значительная подготовка и планирование. Это может быть особенно проблематичным, если вы не настроили Project Server 2010. Поставщики решений Майкрософт могут помочь вам, если вы планируете переход на Project Server 2019 или Project Online. Найдите поставщика решений в [центре поставщиков решений Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Планирование настроек** в среде project Server 2010 может не работать при переходе на project Server 2019 или Project Online. Существует существенные различия архитектуры Project Server между версиями. Кроме того, все необходимые операционные системы, серверы баз данных и веб-браузеры, работающие с версиями, отличаются. Запланируйте, как тестировать или перестраивать настройки в новой среде. Воспользуйтесь этой возможностью, чтобы определить, требуются ли какие-либо настройки. Для получения дополнительных сведений ознакомьтесь [со статьей Создание плана для текущих настроек во время обновления до SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- При планировании, выполнении и тестировании обновления **время и терпение** занимают значительное время и усилия, особенно при обновлении до Project Server 2019. При переходе с Project Server 2010 на Project Server 2019 необходимо сначала перенести данные в Project Server 2013, проверить данные, перенести их в Project Server 2016, а затем в Project Server 2019. Вы можете попытаться узнать у поставщика решений Майкрософт время и оценить затраты на их поддержку.

## <a name="migrate-to-project-online"></a>Миграция в Project Online

Если вы решили выполнить миграцию из Project Server 2010 в Project Online, вы можете выполнить следующие действия, чтобы вручную перенести данные плана проекта:

1. Сохраните планы проекта из Project Server 2010 в MPP формат.

2. Используя Project профессиональный 2016, Project профессиональный 2019 или клиент Project Online для настольных ПК, откройте каждый MPP-файл, а затем сохраните и опубликуйте его в Project Online.

Вы можете вручную создать конфигурацию PWA в Project Online (например, создать все необходимые настраиваемые поля или корпоративные календари). Кроме того, для этого процесса могут помочь поставщики решений Майкрософт.

Основные ресурсы:

|Resource|Описание|
|---|---|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Настройка и использование Project Online|
|[Описание службы Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Сведения о различных доступных планах Project Online|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Переход на новую локальную версию Project Server

Мы настоятельно считаем, что вы получаете лучшие значения и удобство работы пользователей, переполнив их в Project Online. Но мы также понимаем, что в некоторых организациях необходимо хранить данные проекта локально. Если вы решили хранить данные проекта локально, вы можете перенести среду Project Server 2010 в Project Server 2013, Project Server 2016 или Project Server 2019.

Если вы не можете выполнить миграцию в Project Online, рекомендуется выполнить миграцию в Project Server 2019. Project Server 2019 включает в себя большинство основных функций, описанных в предыдущих выпусках Project Server. И наиболее полно соответствует интерфейсу, доступному в Project Online, хотя некоторые функции доступны только в Project Online.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

> [!NOTE]
> Если вы ограничены локальным решением и только миграция выполняется только в Project Server 2013, помните, что в этой версии остается только еще несколько лет поддержки. Дата окончания срока службы Project Server 2013 с пакетом обновления 2 (SP2) от 13 октября 2023 г. Для получения дополнительных сведений о датах окончания поддержки обратитесь к разделу [Политика жизненного цикла продуктов Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Как перейти к Project Server 2019?

Различия в архитектуре Project Server 2010 и Project Server 2019 предотвращают прямой путь миграции. Поэтому необходимо перенести данные Project Server 2010 в каждую последовательную версию Project Server, пока не будет достигнуто приложение Project Server 2019. Действия по обновлению Project Server 2010 до Project Server 2019:

1. Переход на Project Server 2013.

2. Миграция из Project обслуживает 2013 в Project Server 2016.

3. Миграция из Project Server 2016 в Project Server 2019.

После завершения каждой миграции убедитесь, что данные успешно перенесены.

### <a name="step-1-migrate-to-project-server-2013"></a>Шаг 1: миграция на Project Server 2013

Подробную информацию об обновлении Project Server 2010 to Project Server 2013 можно найти в статье [Upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Основные ресурсы:

- [Обзор этапов обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Общие сведения о том, как обновить Project Server 2010 до Project Server 2013 на высоком уровне.
- [Планирование обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Изучите вопросы планирования при обновлении Project Server 2010 до Project Server 2013, включая требования к системе.

- [Новые возможности Project Server 2013 Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) охватывают важные изменения этой версии, в том числе:

   - Обновление на месте до Project Server 2013 отсутствует. Метод с присоединением базы данных поддерживается только для обновления до Project Server 2010 до Project Server 2013.

   - Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но и объединяет четыре базы данных Project Server 2010 в одну базу данных Project Web App.

   - SharePoint Server 2013 и Project Server 2013 изменились на проверку подлинности на основе утверждений из предыдущей версии. Если вы используете классическую проверку подлинности, это необходимо учесть при обновлении. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Основные ресурсы:

- [Общие сведения о процессе обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Схема процесса обновления Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Отличная консолидация баз данных, Project Server 2010 – 2013 миграция на 8 простых действий](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Шаг 2: миграция на Project Server 2016

После перехода на Project Server 2013 и проверки успешности переноса данных необходимо выполнить миграцию в Project Server 2016.

Дополнительные сведения можно найти [в статье Upgrade to Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Основные ресурсы:

- [Обзор процесса обновления до Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Сведения о том, что необходимо сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Просмотрите рекомендации по планированию, которые необходимо выполнить при обновлении Project Server 2013 до Project Server 2016.

Что нужно [знать о сервере Project Server 2016 обновление](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) , в том числе важные изменения для обновления до этой версии, в том числе:

- При создании среды Project Server 2016, обратите внимание на то, что установочные файлы Project Server 2016 включены в SharePoint Server 2016. Дополнительные сведения см. в статье [deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Планы ресурсов являются устаревшими в Project Server 2016. Планы ресурсов Project Server 2013 будут перенесены в задействование ресурсов в Project Server 2016 и Project Online. Для получения дополнительных сведений см. [Обзор: задействование ресурсов](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) .

### <a name="step-3-migrate-to-project-server-2019"></a>Шаг 3: миграция на Project Server 2019

После перехода на Project Server 2016 и проверки успешности переноса данных необходимо перенести данные в Project Server 2019.

Чтобы узнать, что нужно сделать для обновления с Project Server 2016 до Project Server 2019, ознакомьтесь со статьей [обновление до Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Основные ресурсы:

- [Обзор процесса обновления Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Изучите рекомендации по планированию обновления с Project Server 2016 до Project Server 2019.

- [Что нужно знать об обновлении Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Узнайте о важных изменениях для обновления до этой версии, в том числе:

   - В процессе обновления данные из базы данных Project Server 2016 будут перенесены в базу данных контента SharePoint Server 2019.  Project Server 2019 больше не будет создавать собственную базу данных Project Server в ферме SharePoint Server.

   - После обновления следует учитывать несколько изменений в Project Web App.  Сведения о новых возможностях [Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Другие ресурсы**:

- [Описания служб Project Online](https://go.microsoft.com/fwlink/p/?linkid=841280): сведения о функциях управления портфелем, включенных в project Server 2016 и Project Online Premium.

- [Руководство по миграции Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Обзор параметров для клиентов и серверов Office 2010 и Windows 7

Визуальное представление возможностей обновления, миграции и перехода на облачные решения для клиентов и серверов Office 2010, а также Windows 7 см. на плакате [Прекращение поддержки](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Завершение поддержки клиентов и серверов Office 2010 и афиши Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

На этом плакате показаны различные пути, которые можно предпринять, чтобы избежать завершения поддержки клиентских и серверных продуктов Office 2010 и Windows 7, с предпочитаемыми путями и поддержкой параметров в Microsoft 365 корпоративный выделенный.

Вы также можете [скачать](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) этот плакат и напечатать его в формате Letter, Legal или таблоид (11 x 17).

## <a name="related-topics"></a>Статьи по теме

[Переход с SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Обновление серверов и клиентов Office 2010](upgrade-from-office-2010-servers-and-products.md)
