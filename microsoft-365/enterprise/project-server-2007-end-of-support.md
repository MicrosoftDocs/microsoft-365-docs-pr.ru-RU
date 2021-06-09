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
description: 10 октября 2017 г. завершилась поддержка Project Server 2007, Project Portfolio Server и Project 2007 г. Используйте эту статью для планирования обновления.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927352"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2007;

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Поддержка завершилась Office 2007 серверов и приложений в 2017 г., и необходимо рассмотреть планы по миграции. Если вы в настоящее время используете Project Server 2007 и связанные с ними продукты, обратите внимание на следующие даты окончания поддержки:
  
|**Продукт**|**Конец даты поддержки**|
|:-----|:-----|
|Project Server 2007  <br/> |10 октября 2017 г.  <br/> |
|Project Portfolio Server 2007  <br/> |10 октября 2017 г.  <br/> |
|Project 2007 standard  <br/> |10 октября 2017 г.  <br/> |
|Project 2007 Professional  <br/> |10 октября 2017 г.  <br/> |
   
Дополнительные сведения о Office 2007 серверов, достигающих выхода на пенсию, см. в Office [2007](upgrade-from-office-2007-servers-and-products.md)серверов и клиентских продуктов.
  
## <a name="what-does-end-of-support-mean"></a>Что означает *конец поддержки?*

Большинство продуктов Майкрософт имеют жизненный цикл поддержки, в ходе которого они получают новые функции, исправления ошибок, исправления безопасности и так далее. Этот жизненный цикл обычно длится 10 лет с начального выпуска продукта. Конец жизненного цикла называется завершением поддержки продукта. Так Project 10 октября 2017 г. корпорация Майкрософт больше не предоставляет:
  
- Техническая поддержка проблем, которые могут возникнуть.
    
- Ошибка устраняет проблемы, которые могут повлиять на стабильность и доступность сервера.
    
- Устранение уязвимостей, которые могут сделать сервер уязвимым для нарушений безопасности.
    
- Обновления часовой зоны.
    
Установка Project Server 2007 продолжится после этой даты. Но из-за изменений, перечисленных ранее, настоятельно рекомендуется перейти с Project Server 2007 сразу же после практического применения.
  
## <a name="what-are-my-options"></a>Какие у меня варианты?

Если вы используете Project Server 2007, необходимо изучить варианты миграции, которые:
  
- Миграция в Project Online
    
- Миграция в более новую локальной версии Project Server (предпочтительно Project Server 2016)
    
|**Почему я предпочитаю перейти на Project Online**|**Почему я предпочитаю перейти на Project Server 2016**|
|:-----|:-----|
| У меня есть мобильные пользователи.  <br/> <br/>Значительные затраты на перенос (оборудование, программное обеспечение, часы и усилия по реализации). <br/><br/>  После переноса основными задачами являются затраты на поддержание среды (например, автоматическое обновление, гарантированное время простоя и так далее).  <br/> | Бизнес-правила ограничивают работу бизнеса в облаке.<br/><br/>  Мне нужен контроль над обновлениями в своей среде.  |
   
> [!NOTE]
> Дополнительные сведения о вариантах перехода с Office серверов 2007 г. см. в справке Ресурсы, которые помогут вам обновиться с Office серверов и клиентов [2007 г.](upgrade-from-office-2007-servers-and-products.md) Обратите внимание, Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут делиться одинаковым пулом ресурсов. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Важные факторы при переносе Project Server 2007

При планировании миграции с Project Server 2007 рассмотрим следующее:
  
- **Получить помощь от партнера Майкрософт** . Обновление Project Server 2007 может быть сложной задачей и требует большой подготовки и планирования. Это может быть особенно сложно, если вы изначально не Project Server 2007. К счастью, есть партнеры Майкрософт, которые могут помочь, планируете ли вы перейти в Project Server 2016 или Project Online. Поиск партнера Майкрософт, который поможет вам в миграции в [Центре партнеров Майкрософт.](https://go.microsoft.com/fwlink/p/?linkid=841249) Поиск по термину *Gold Project и управление* портфелем, чтобы просмотреть список всех партнеров Майкрософт, которые имеют опыт Project. 
    
- **Планирование настроек** . Многие из настроек, которые вы сделали в среде Project Server 2007, могут не работать при миграции в Project Server 2016 или Project Online. Существуют значительные различия в архитектуре Project Server между версиями. Также отличаются необходимые операционные системы, серверы баз данных и клиентские веб-браузеры, поддерживаемые. Планирование тестирования или восстановления настроек для новой среды. Планирование также предоставляет хорошую возможность для рассмотрения необходимости каждой настройки. Дополнительные сведения см. в рублях Создание плана текущих настроек во время обновления [SharePoint 2013 г.](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013) 
    
- **Время и терпение** — планирование обновления, выполнение и тестирование будут отбирать время и усилия, особенно если вы Project Server 2016. Например, если вы мигрируете с Project Server 2007 на Project Server 2016, сначала необходимо перейти на Project Server 2010, проверить данные, а затем сделать то же самое при миграции в каждой последовательной версии. Возможно, вам нужно проверить у партнера Майкрософт, чтобы получить оценки того, сколько времени это займет и сколько это будет стоить.
    
## <a name="migrate-to-project-online"></a>Миграция в Project Online

Если вы решите перейти с Project Server 2007 на Project Online, вы можете сделать следующее, чтобы вручную перенести данные плана проекта:
  
1. Сохраните планы проекта с Project Server 2003 до формата MPP.
    
2. В Project профессиональный 2013 Project профессиональный 2016 или Project Online desktop Client откройте каждый файл MPP, а затем сохраните и опубликуй его Project Online.
    
Вы можете вручную создать конфигурацию Microsoft Project (PWA) в Project Online. Например, воссоздать необходимые настраиваемые поля или корпоративные календари. Партнеры Майкрософт также могут помочь в этом процессе.
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Настройка и использование Project Online <br/> |
|[Project Online Описания служб](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Сведения о различных планах Project Online, доступных для вас <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Перенос в более новую локальной версии Project Server

Мы твердо верим, что вы получите лучшее значение и пользовательский опыт, переехав в Project Online. Но мы также понимаем, что некоторым организациям необходимо хранить данные о проекте в локальной среде. Если вы решите сохранить данные проекта на локальной основе, вы можете перенести среду Project Server 2007 в Project Server 2010, Project Server 2013 или Project Server 2016.
  
Если вы не можете перейти в Project Online, рекомендуем перейти в Project Server 2016. Project Server 2016 включает все функции предыдущих выпусков Project Server. Это наиболее близко соответствует опыту, доступному с Project Online, хотя некоторые функции доступны только в Project Online.
  
После каждой миграции необходимо проверить успешное перенос данных.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Как перейти на Project Server 2016?

Архитектурные различия между Project Server 2007 и Project Server 2016 предотвратить прямой путь миграции. Поэтому необходимо перенести данные Project Server 2007 в каждую сеяную версию Project Server, пока не достигнете Project Server 2016.
  
Выполните следующие действия, чтобы Project Server 2016:
  
1. Перенос с Project Server 2007 на Project Server 2010.
    
2. Перенос с Project Serve 2010 на Project Server 2013.
    
3. Перенос с Project Server 2013 на Project Server 2016.
    
После каждой миграции убедитесь, что данные успешно переносились.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Шаг 1. Миграция Project Server 2007 на Project Server 2010

Полное описание того, что необходимо сделать для обновления с Project Server 2007 до Project Server 2010, см. в обзоре [Upgrade to Project Server 2010.](/previous-versions/office/project-server-2010/gg502590(v=office.14))
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Project Обзор обновления server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Представление о том, что необходимо сделать для обновления с Project Server 2007 до Project Server 2010 <br/> |
|[План обновления до Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Планирование при обновлении с Project Server 2007 до Project Server 2010, включая требования к системе  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Как обновить?

Подробные сведения см. в [Project Server 2010.](/previous-versions/office/project-server-2010/gg502590(v=office.14)) Но важно понимать, что для обновления можно использовать два различных метода:
  
- **Обновление с присоединением к базе данных:** Этот метод обновляет только содержимое для среды, а не параметры конфигурации. Это необходимо, если вы обновляете сервер Office Project Server 2007, развернутого на оборудовании, которое поддерживает только 32-битную операционную систему сервера. Существует два типа методов обновления с присоединением к базе данных:
    
  - Полное обновление с присоединением к базе данных — перенос данных проекта, хранимого в базах данных Office Project Server 2007, а также данных **веб-Microsoft Project** приложений, хранимых в базе данных SharePoint контента.
    
  - **Обновление *ядра с*** присоединением к базе данных — миграция только данных проекта, хранимого в базах данных Project Server.
    
- **Обновление на месте.** Данные конфигурации фермы и весь контент фермы обновляются на существующем оборудовании в фиксированном порядке. При запуске процесса обновления настройка отнимает всю ферму в автономном режиме. Веб-сайты и Microsoft Project веб-приложения недоступны до завершения обновления, а затем настройка перезапуска сервера. После начала обновления на месте нельзя приостановить обновление или откатиться к предыдущей версии. Лучше всего сделать зеркальное изображение производственной среды и обновить ее на месте, а не в производственной среде. 
    
Дополнительные ресурсы:
  
- [SuperFlow для обновления Microsoft Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Миграция Project Server 2007 на Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Вопросы обновления, связанные с веб-частями Project Web App](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Набор разработки программного обеспечения (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Шаг 2. Перенос Project Server 2013

После проверки успешного переноса данных на сервер Project Server 2013.
  
Полное описание действий по обновлению с Project Server 2010 до Project Server 2013 см. в Project [Server 2013.](/project/upgrade-to-project-server-2016) 
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор этапов обновления до Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Обзор того, что необходимо сделать для обновления с Project Server 2010 до Project Server 2013  <br/> |
|[План обновления до Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Планирование при обновлении с Project Server 2010 до Project Server 2013, включая требования к системе <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Что нужно знать о обновлении до этой версии

[Новое обновление Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) описывает важные изменения для обновления для этой версии. Наиболее заметными являются: 
  
- Обновление на месте до Project Server 2013 не происходит. Метод прикрепления к базе данных — это единственный поддерживаемый метод обновления с Project Server 2010 до Project Server 2013.
    
- Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но и консолидирует четыре базы данных Project Server 2010 в одну базу данных Project Web App.
    
- В версиях 2013 SharePoint Server и Project Server изменились на проверку подлинности на основе утверждений. Если вы используете классическую проверку подлинности, необходимо учитывать этот фактор для обновления. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
Дополнительные ресурсы:
  
- [Общие сведения о процессе обновления до Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project Схема процесса обновления сервера](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Большая консолидация баз данных, Project Server 2010 до 2013 Миграция в 8 простых шагах](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Шаг 3. Миграция на Project Server 2016

После проверки успешного переноса данных в Project Server 2016.
  
Полное описание действий по обновлению с Project Server 2013 до Project Server 2016 см. в Project Server 2016 [.](//project/upgrading-to-project-server-2016)
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор процесса обновления до Project Server 2016](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Обзор того, что необходимо сделать для обновления с Project Server 2013 до Project Server 2016 <br/> |
|[Планирование обновления до Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Планирование соображений, которые необходимо обновить с Project Server 2013 до Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Что нужно знать о обновлении до этой версии

Все, что необходимо знать о [Project Server 2016 обновлении,](/project/plan-for-upgrade-to-project-server-2016) рассказывает о некоторых важных изменениях для обновления для этой версии, которые включают:
  
- При создании Project Server 2016 среды, в которую будут перенесены данные Project Server 2013, файлы Project Server 2016 установки включаются в SharePoint Server 2016. Дополнительные сведения см. в [Project Server 2016.](/project/deploy-project-server-2016)
    
- Планы ресурсов в Project Server 2016. Планы ресурсов Project Server 2013 будут перенесены в Project Server 2016 и Project Online. Дополнительные сведения см. в [обзоре.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 
    
## <a name="migrate-from-portfolio-server-2007"></a>Перенос с Portfolio Server 2007

Project Portfolio Server 2007 использовался Project Server 2007 для стратегии портфеля, приоритетов и оптимизации. Дополнительные версии Project Portfolio Server не создавались после этой версии. Однако функции управления портфелями доступны в Project Server 2016 и Premium версии Project Online. Но данные из Project Portfolio Server 2007 не могут быть перенесены в любой из них. Необходимо воссоздать такие данные, как бизнес-драйверы.
  
Другие ресурсы
  
- [Project Online службы:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) См. функции управления портфелями, включенные в Project Server 2016 и Project Online расширенный.
    
- [Microsoft Office Project руководство по миграции Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Статьи по теме

[SharePoint Завершение плана поддержки Server 2007](sharepoint-2007-end-of-support.md)
  
[Ресурсы, которые помогут вам обновиться с Office серверов и клиентов 2007 г.](upgrade-from-office-2007-servers-and-products.md)
