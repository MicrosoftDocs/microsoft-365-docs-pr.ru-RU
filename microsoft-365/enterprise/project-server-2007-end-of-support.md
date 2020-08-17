---
title: План действий после прекращения поддержки Project Server 2007;
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
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
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: 10 октября 2017 г. поддержка закончилась для Project Server 2007, Project Portfolio Server и Project 2007. Используйте эту статью для планирования обновления сейчас.
ms.openlocfilehash: 81588f803813d0da938d709e93e26b7dadc3b993
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696456"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2007;

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Поддержка для серверов и приложений Office 2007 в 2017, и вам необходимо рассмотреть план миграции. Если в настоящее время используется Project Server 2007, обратите внимание на то, что этот продукт и другие связанные продукты имеют следующие даты окончания поддержки:
  
|**Product**|**Дата окончания поддержки**|
|:-----|:-----|
|Project Server 2007  <br/> |10 октября 2017 г.  <br/> |
|Project Portfolio Server 2007  <br/> |10 октября 2017 г.  <br/> |
|Project 2007 Стандартный  <br/> |10 октября 2017 г.  <br/> |
|Project 2007 профессиональный  <br/> |10 октября 2017 г.  <br/> |
   
Для получения дополнительных сведений о серверах Office 2007, которые достигают выбытие, ознакомьтесь со статьей [обновление с серверов и клиентских продуктов office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Что означает окончание поддержки?

Project Server, как и почти все продукты Майкрософт, имеет жизненный цикл поддержки, в котором мы предоставляем новые функции, исправления ошибок, исправления для системы безопасности и т. д. Этот жизненный цикл обычно продолжается в течение 10 лет с даты первоначального выпуска продукта, а окончание этого жизненного цикла называется окончанием поддержки продукта. Так как Project Server 2007 достиг конца поддержки 10 октября 2017, корпорация Майкрософт больше не предоставляет:
  
- Техническая поддержка проблем, которые могут возникнуть.
    
- Исправление ошибок для обнаруженных проблем, которые могут повлиять на стабильность и удобство использования сервера.
    
- Исправления для системы безопасности уязвимостей, которые могут привести к уязвимости сервера при нарушении безопасности.
    
- Обновления часового пояса.
    
Установка Project Server 2007 продолжит работу после этой даты. Однако из-за перечисленных выше изменений настоятельно рекомендуется выполнить миграцию из Project Server 2007 как можно скорее.
  
## <a name="what-are-my-options"></a>Что такое параметры?

Если вы используете Project Server 2007, необходимо ознакомиться с параметрами миграции, которые перечислены ниже.
  
- Миграция в Project Online
    
- Переход на более новую локальную версию Project Server (желательно Project Server 2016).
    
|**Зачем переходить на Project Online**|**Зачем переходить на Project Server 2016**|
|:-----|:-----|
| У меня есть мобильные пользователи.  <br/>  Затраты на перенос — это большая проблема (оборудование, программное обеспечение, часы и усилия для реализации и т. д.).  <br/>  После миграции затраты на поддержание среды очень важны (например, автоматическое обновление, гарантированное время работы и т. д.).  <br/> | Бизнес-правила ограничивают меня рабочими моими предприятиями в облаке.  <br/>  Мне нужно управлять обновлениями в моей среде.  <br/> |
   
> [!NOTE]
> Для получения дополнительных сведений о возможностях перехода с серверов Office 2007, ознакомьтесь со статьей [ресурсы, которые помогут вам выполнить обновление серверов и клиентов office 2007](upgrade-from-office-2007-servers-and-products.md). Обратите внимание, что Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут совместно использовать один пул ресурсов. 
  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2007"></a>Важные замечания, которые необходимо принять во время планирования миграции из Project Server 2007

При планировании миграции из Project Server 2007 необходимо учитывать следующие рекомендации.
  
- **Получение помощи от партнеров Майкрософт** — обновление с Project Server 2007 может быть проблематичным и требует большого количества подготовки и планирования. Это может быть особенно сложным, если вы не использовались для настройки и первоначально настроили Project Server 2007. К счастью, у вас есть партнеры Майкрософт, которые помогут вам сделать это, если вы планируете переход на Project Server 2016 или Project Online. Вы можете выполнить поиск партнера Майкрософт, который поможет вам выполнить миграцию в [центре партнеров Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841249). Вы можете получить список всех партнеров Майкрософт с опытом в Project, выполнив поиск по термину "  *Золотой проект и управление портфелем*  ". 
    
- **Запланируйте настройки** , имейте в виду, что многие настройки, работающие в среде project Server 2007, могут не работать при переходе на project Server 2016 или Project Online. В архитектуре Project Server существуют существенные различия между версиями, а также операционные системы, серверы баз данных и клиентские веб-браузеры, которые поддерживают работу с более новой версией. Составьте план, чтобы проверить или перестроить настройки по мере необходимости в новой среде. При планировании обновления также будет полезно проверить, действительно ли требуется определенная настройка при переходе вперед. [Создайте план для текущих настроек во время обновления до SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061) содержит общие сведения об оценке и планировании текущих настроек при обновлении. 
    
- При планировании, выполнении и тестировании обновления **время и терпение** занимают много времени и сил, особенно при обновлении до Project Server 2016. Например, при переносе из Project Server 2007 в Project Server 2016 необходимо выполнить миграцию из Project Server 2007 в Project Server 2010, а затем проверить данные, а затем выполнить те же действия при переходе к каждой последующей версии. Вы можете узнать у партнера корпорации Майкрософт, что нужно сравнить ваши затраты с оценками того, сколько времени потребуется для их выполнения, а также в каких затратах. 
    
## <a name="migrate-to-project-online"></a>Миграция в Project Online

Если вы решили выполнить миграцию из Project Server 2007 в Project Online, можно выполнить следующие действия, чтобы вручную перенести данные плана проекта:
  
1. Сохраните планы проекта из Project Server 2003. Формат MPP.
    
2. Используя Project профессиональный 2013, Project профессиональный 2016 или клиент Project Online для настольных ПК, откройте каждый MPP-файл, а затем сохраните и опубликуйте его в Project Online.
    
Вы можете вручную создать конфигурацию PWA в Project Online (например, создать все необходимые настраиваемые поля или корпоративные календари). Кроме того, вы можете помочь партнерам Майкрософт.
  
Основные ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Настройка и использование Project Online.  <br/> |
|[Описания служб Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Сведения о различных доступных планах Project Online.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Переход на новую локальную версию Project Server

Несмотря на то, что вы уверены, что вы можете добиться наилучшего качества и удобства работы пользователей, переполнив их в Project Online, мы также понимаем, что в некоторых организациях необходимо хранить данные проекта в локальной среде. Если вы решили хранить данные проекта локально, вы можете перенести среду Project Server 2007 в Project Server 2010, Project Server 2013 или Project Server 2016.
  
Рекомендуется выполнить миграцию в Project Server 2016, если вы не можете выполнить миграцию в Project Online. Project Server 2016 включает все функции и улучшения, включенные в предыдущие выпуски Project Server, и наиболее точно соответствует интерфейсам, доступным в Project Online (хотя некоторые функции доступны только в Project Online).
  
После завершения каждой миграции необходимо проверить данные, чтобы убедиться, что они успешно перенесены.
  
> [!NOTE]
> Если вы планируете переход на Project Server 2010 только в том случае, если вы ограничены локальным решением, то важно отметить, что осталось только еще несколько лет поддержки. Дата окончания поддержки Project Server 2010 с пакетом обновления 2 (SP2) — 10/13/2020. Для получения дополнительных сведений о конце дат поддержки обратитесь к разделу [Политика жизненного цикла продуктов Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Как перейти к Project Server 2016?

Различия в архитектуре Project Server 2007 и Project Server 2016 запрещают прямой путь миграции. Это означает, что после обновления до Project Server 2016 вам потребуется перенести данные Project Server 2007 в следующую последующую версию Project Server.
  
Для обновления до Project Server 2016 вам потребуется выполнить следующие действия:
  
1. Шаг 1: миграция из Project Server 2007 в Project Server 2010.
    
2. Шаг 2: миграция из Project обслуживает 2010 в Project Server 2013.
    
3. Шаг 3: миграция из Project Server 2013 в Project Server 2016.
    
После завершения каждой миграции необходимо проверить данные, чтобы убедиться, что они успешно перенесены.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Шаг 1: миграция из Project Server 2007 в Project Server 2010

Подробные сведения о том, что нужно сделать для обновления Project Server 2007 до Project Server 2010, можно найти в статье [обновление до Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) Set на сайте TechNet. 
  
Основные ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор обновления Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2007 до Project Server 2010.  <br/> |
|[Планирование обновления до Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Изучите рекомендации по планированию, которые необходимо выполнить при обновлении Project Server 2007 до Project Server 2010, включая требования к системе.  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Как выполнить обновление?

Подробные сведения об обновлении можно найти в наборе содержимого [обновление до Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) , поэтому необходимо понимать, что существует два отдельных метода, которые можно использовать для обновления: 
  
- **Обновление с присоединением баз данных:** Этот метод обновляет только содержимое вашей среды, а не параметры конфигурации. Это необходимо при обновлении с Office Project Server 2007, развернутого на оборудовании, поддерживающем только серверную операционную систему 32. Существует два типа методов обновления с присоединением баз данных: 
    
  - **Полное обновление с присоединением базы данных** — перенос данных проекта, хранящихся в базах данных Office project Server 2007, а также данных сайта Microsoft Project Web App (PWA), хранящихся в базе данных контента SharePoint. 
    
  - **Базовое обновление с присоединением баз данных** — перенос только данных проекта, хранящихся в базах данных Project Server. 
    
- **Обновление на месте**: данные конфигурации для фермы и всего контента фермы обновляются на имеющемся оборудовании в фиксированном порядке. При запуске процесса обновления на месте программа установки переводит всю ферму в автономный режим, а веб-сайты и сайты Microsoft Project Web App будут недоступны до завершения обновления, а затем программа установки перезапускает сервер. После запуска обновления на месте нельзя приостановить обновление или сделать откат до предыдущей версии. Настоятельно рекомендуется сделать зеркальное изображение рабочей среды и выполнить обновление на месте для этой среды, а не для рабочей среды. 
    
Дополнительные ресурсы:
  
- [Автоперетекание для обновления Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Миграция из Project Server 2007 в Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Вопросы обновления, связанные с веб-частями Project Web App](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Пакет средств разработки программного обеспечения (SDK) для Project](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Шаг 2: миграция на Project Server 2013

После перехода на Project Server 2010 и проверки того, что данные успешно перенесены, следующим шагом является перенос данных в Project Server 2013.
  
Подробные сведения о том, что нужно сделать для обновления Project Server 2010 до Project Server 2013, можно найти в статье [обновление до Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) Set на сайте TechNet. 
  
Основные ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор этапов обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2010 до Project Server 2013.  <br/> |
|[Планирование обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Изучите рекомендации по планированию, которые необходимо выполнить при обновлении Project Server 2010 до Project Server 2013, включая требования к системе.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Сведения об обновлении до этой версии

[Что нового в Project Server 2013 Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) сообщает о важных изменениях для обновления этой версии, что наиболее заметно: 
  
- Обновление на месте до Project Server 2013 отсутствует. Метод с присоединением базы данных — единственный поддерживаемый метод обновления с Project Server 2010 до Project Server 2013.
    
- Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но также объединяет четыре базы данных Project Server 2010 в одну базу данных Project Web App.
    
- SharePoint Server 2013 и Project Server 2013 изменились на проверку подлинности на основе утверждений из предыдущей версии. При использовании классической проверки подлинности необходимо принять во внимание рекомендации по обновлению. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Дополнительные ресурсы:
  
- [Общие сведения о процессе обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Схема процесса обновления Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Отличная консолидация баз данных, Project Server 2010 – 2013 миграция на 8 простых действий](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Шаг 3: миграция на Project Server 2016

После перехода на Project Server 2013 и проверки того, что данные успешно перенесены, следующим шагом является перенос данных в Project Server 2016.
  
Подробные сведения о том, что нужно сделать для обновления Project Server 2013 до Project Server 2016, можно найти в статье обновление до Project Server 2016 Set на сайте TechNet.
  
Основные ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор процесса обновления до Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2013 до Project Server 2016.  <br/> |
|[Планирование обновления до Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Изучите вопросы планирования, которые необходимо выполнить при обновлении Project Server 2013 до Project Server 2016, включая.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Сведения об обновлении до этой версии

Что нужно [знать об обновлении Project Server 2016, чтобы](https://go.microsoft.com/fwlink/p/?linkid=841827) получить сведения о важных изменениях для этой версии, в том числе: 
  
- При создании среды Project Server 2016, в которую будут перенесены данные Project Server 2013, обратите внимание на то, что установочные файлы Project Server 2016 включены в SharePoint Server 2016. Дополнительные сведения см. в статье [deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Планы ресурсов являются устаревшими в Project Server 2016. Планы ресурсов Project Server 2013 будут перенесены в задействование ресурсов в Project Server 2016 и Project Online. Для получения дополнительных сведений см. [Обзор: задействование ресурсов](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
## <a name="migrate-from-portfolio-server-2007"></a>Миграция с сервера Portfolio Server 2007

Project Portfolio Server 2007 использовался с Project Server 2007 для стратегии, определения приоритетов и оптимизации портфеля. После этой версии не были созданы дополнительные версии Project Portfolio Server. Однако функции управления портфелем доступны как в Project Server 2016, так и в расширенной версии Project Online. Данные из Project Portfolio Server 2007 не могут быть перенесены в. Для таких данных, как бизнес-факторы, потребуется повторное создание.
  
Другие ресурсы
  
- [Описания служб Project Online](https://go.microsoft.com/fwlink/p/?linkid=841280): сведения о функциях управления портфелем, включенных в project Server 2016 и Project Online Premium.
    
- [Руководство по миграции Microsoft Office Project Portfolio Server 2007](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Связанные статьи

[План поддержки SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Ресурсы, помогающие выполнить обновление серверов и клиентов Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
