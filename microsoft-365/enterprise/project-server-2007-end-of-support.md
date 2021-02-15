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
description: 10 октября 2017 г. поддержка Project Server 2007, Project Portfolio Server и Project 2007 завершена. Используйте эту статью для планирования обновления.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519803"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2007;

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Поддержка серверов и приложений Office 2007 завершена в 2017 г., и необходимо рассмотреть планы миграции. Если вы в настоящее время используете Project Server 2007 и связанные продукты, обратите внимание на следующие даты окончания поддержки:
  
|**Product**|**Дата окончания поддержки**|
|:-----|:-----|
|Project Server 2007  <br/> |10 октября 2017 г.  <br/> |
|Project Portfolio Server 2007  <br/> |10 октября 2017 г.  <br/> |
|Project 2007 Standard  <br/> |10 октября 2017 г.  <br/> |
|Project 2007 Профессиональный  <br/> |10 октября 2017 г.  <br/> |
   
Дополнительные сведения о серверах Office 2007, достигающих выхода из системы, см. в под вопросе "Обновление с серверов [Office 2007 и клиентских продуктов".](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>Что означает *окончание поддержки?*

Большинство продуктов Майкрософт имеют жизненный цикл поддержки, в течение которого они получают новые функции, исправления ошибок, исправления безопасности и так далее. Этот жизненный цикл обычно длится 10 лет с начального выпуска продукта. Завершение этого жизненного цикла называется завершением поддержки продукта. Так как Project Server 2007 перестал поддерживаться 10 октября 2017 г., корпорация Майкрософт больше не предоставляет:
  
- Техническая поддержка для проблем, которые могут возникнуть.
    
- Исправления ошибок, которые могут повлиять на стабильность и доступность сервера.
    
- Исправления безопасности для уязвимостей, которые могут сделать сервер уязвимым к нарушению безопасности.
    
- Обновления часовой пояс.
    
Установка Project Server 2007 продолжится после этой даты. Но из-за изменений, перечисленных выше, настоятельно рекомендуется как можно скорее перейти с Project Server 2007.
  
## <a name="what-are-my-options"></a>Какие у меня есть варианты?

Если вы используете Project Server 2007, вам необходимо изучить варианты миграции, которые:
  
- Переход на Project Online
    
- Переход на более новую версию Project Server (предпочтительно Project Server 2016)
    
|**Почему я хочу перейти на Project Online**|**Почему я хочу перейти на Project Server 2016**|
|:-----|:-----|
| У меня есть мобильные пользователи.  <br/> <br/>Стоимость переноса является серьезной проблемой (оборудование, программное обеспечение, часы и усилия по внедрению). <br/><br/>  После миграции основными задачами являются затраты на обслуживание среды (например, автоматическое обновление, гарантированное время работы и так далее).  <br/> | Бизнес-правила ограничивают работу моей компании в облаке.<br/><br/>  Мне нужно управлять обновлениями в своей среде.  |
   
> [!NOTE]
> Дополнительные сведения о вариантах перехода с серверов Office 2007 см. в справке по обновлению с серверов и клиентов [Office 2007.](upgrade-from-office-2007-servers-and-products.md) Обратите внимание, что Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут совместно использовать один пул ресурсов. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Важные вопросы при миграции с Project Server 2007

При планировании миграции с Project Server 2007 учитывайте следующее:
  
- **Получите помощь от партнера Майкрософт.** Обновление Project Server 2007 может быть сложной задачей и требует большой подготовки и планирования. Это может оказаться особенно сложной задачей, если вы не были человеком, который изначально настроил Project Server 2007. К счастью, существуют партнеры Майкрософт, которые могут помочь при переходе на Project Server 2016 или Project Online. Найщите партнера Майкрософт, который поможет вам с миграцией в [Центре партнеров Майкрософт.](https://go.microsoft.com/fwlink/p/?linkid=841249) Поиск по термину  *Gold Project and Portfolio Management,* чтобы просмотреть список всех партнеров Майкрософт, которые имеют опыт работы с Project. 
    
- **Планирование настроек.** Многие настройки, сделанные в среде Project Server 2007, могут не работать при переходе на Project Server 2016 или Project Online. В архитектуре Project Server существуют значительные различия между версиями. Поддерживаемые операционные системы, серверы баз данных и клиентские веб-браузеры также отличаются. Планирование тестирования или перестроения настроек для новой среды. Планирование также дает хорошую возможность учесть, требуется ли по-прежнему каждая настройка. Дополнительные сведения см. в сведениях о создании плана текущих настроек во время [обновления до SharePoint 2013.](https://go.microsoft.com/fwlink/p/?linkid=842061) 
    
- **Время и терпение.** Планирование, выполнение и тестирование обновлений займет много времени и усилий, особенно при обновлении до Project Server 2016. Например, при переходе с Project Server 2007 на Project Server 2016 сначала необходимо перейти на Project Server 2010, проверить данные, а затем сделать то же самое при переходе на каждую из последовательных версий. Вам может потребоваться уточнить у партнера Майкрософт оценку того, сколько времени это займет и сколько это будет стоить.
    
## <a name="migrate-to-project-online"></a>Переход на Project Online

Если вы решили перейти с Project Server 2007 на Project Online, можно сделать следующее, чтобы вручную перенести данные плана проекта:
  
1. Сохраните планы проекта из Project Server 2003 в формат MPP.
    
2. В Project профессиональный 2013, Project профессиональный 2016 или клиенте Project Online для настольных ПК откройте каждый MPP-файл, а затем сохраните и опубликуем его в Project Online.
    
Вы можете вручную создать конфигурацию Microsoft Project Web App (PWA) в Project Online. Например, воссоздать все необходимые настраиваемые поля или корпоративные календари. Партнеры Майкрософт также могут помочь в этом процессе.
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Настройка и использование Project Online <br/> |
|[Описание службы Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Сведения о различных доступных планах Project Online <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Переход на более новую версию Project Server в локальной версии

Мы настоятельно верим, что переход на Project Online будет наиболее удобным и удобным для пользователя. Однако мы также понимаем, что некоторым организациям необходимо хранить данные проекта в локальной среде. Если вы решили хранить данные проекта локально, можно перенести среду Project Server 2007 в Project Server 2010, Project Server 2013 или Project Server 2016.
  
Если вы не можете перейти на Project Online, рекомендуется перейти на Project Server 2016. Project Server 2016 включает все функции предыдущих выпусков Project Server. Он наиболее точно соответствует возможностям Project Online, хотя некоторые функции доступны только в Project Online.
  
После каждой миграции следует проверить, успешно ли перенесены данные.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Как перейти на Project Server 2016?

Архитектурные различия между Project Server 2007 и Project Server 2016 препятствуют прямому пути миграции. Поэтому необходимо перенести данные Project Server 2007 на каждую поотивную версию Project Server, пока не достигнете Project Server 2016.
  
Выполните следующие действия в Project Server 2016:
  
1. Миграция с Project Server 2007 на Project Server 2010.
    
2. Миграция с Project Serve 2010 на Project Server 2013.
    
3. Миграция с Project Server 2013 на Project Server 2016.
    
После каждой миграции убедитесь, что данные успешно перенесены.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Шаг 1. Миграция с Project Server 2007 на Project Server 2010

Полное описание действий по обновлению Project Server 2007 до Project Server 2010 см. в описании обновления до [Project Server 2010.](https://go.microsoft.com/fwlink/p/?linkid=841812)
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор обновления Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Высокоуровневый обзор того, что необходимо сделать для обновления Project Server 2007 до Project Server 2010 <br/> |
|[Планирование обновления до Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Вопросы планирования при обновлении Project Server 2007 до Project Server 2010, включая требования к системе  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Как обновиться?

Подробные сведения [см. в обновлении до Project Server 2010.](https://go.microsoft.com/fwlink/p/?linkid=841812) Однако важно понимать, что для обновления можно использовать два разных метода:
  
- **Обновление с перенастройки баз данных:** Этот метод обновляет только содержимое среды, а не параметры конфигурации. Это необходимо при обновлении Office Project Server 2007, развернутого на оборудовании, которое поддерживает только 32-битную серверную операционную систему. Существует два типа методов обновления с перенастройки баз данных:
    
  - **** Полное обновление с присоединением баз данных . Перенос данных проекта, хранимого в базах данных Office Project Server 2007, а также данных сайта Microsoft Project Web App, хранимые в базе данных контента SharePoint.
    
  - **Обновление с *присоединением баз*** данных — перенос только данных проекта, хранимого в базах данных Project Server.
    
- **Обновление на месте:** данные конфигурации фермы и весь контент фермы обновляются на существующем оборудовании в фиксированном порядке. При запуске процесса обновления все фермы перенабирается в автономный режим. Веб-сайты и сайты Microsoft Project Web App будут недоступны до завершения обновления, а затем программа установки перезапустит сервер. После начала обновления на месте нельзя приостановить обновление или вернуться к предыдущей версии. Лучше всего сделать зеркальное изображение производственной среды и обновить ее на месте, а не в производственной среде. 
    
Дополнительные ресурсы:
  
- [SuperFlow для обновления Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Миграция с Project Server 2007 на Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Вопросы обновления, связанные с веб-частями Project Web App](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Пакет средств разработки программного обеспечения Project (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Шаг 2. Миграция на Project Server 2013

После проверки успешного переноса данных необходимо перейти на Project Server 2013.
  
Полное описание действий по обновлению Project Server 2010 до Project Server 2013 см. в описании обновления до [Project Server 2013.](https://go.microsoft.com/fwlink/p/?linkid=841822) 
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор этапов обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Обзор того, что необходимо сделать для обновления Project Server 2010 до Project Server 2013  <br/> |
|[Планирование обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Вопросы планирования при обновлении Project Server 2010 до Project Server 2013, включая требования к системе <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Что нужно знать об обновлении до этой версии

[Новые возможности обновления Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) описывают важные изменения, внесенные в обновление для этой версии. Наиболее важные из них: 
  
- Обновление на месте до Project Server 2013 не происходит. Метод с перенастройки баз данных — единственный поддерживаемый метод обновления с Project Server 2010 до Project Server 2013.
    
- Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но и объединяет четыре базы данных Project Server 2010 в одну Project Web App данных.
    
- В версиях 2013 SharePoint Server и Project Server были изменены на проверку подлинности на основе утверждений. Если вы используете классическую проверку подлинности, необходимо учитывать этот фактор для обновления. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Дополнительные ресурсы:
  
- [Общие сведения о процессе обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Схема процесса обновления Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Большая консолидация баз данных, перенос Project Server 2010 на 2013 за 8 простых шагов](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Шаг 3. Миграция на Project Server 2016

После проверки успешного переноса данных необходимо перейти на Project Server 2016.
  
Полное описание действий по обновлению Project Server 2013 до Project Server 2016 см. в описании обновления до [Project Server 2016.](https://docs.microsoft.com//project/upgrading-to-project-server-2016)
  
Ключевые ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Обзор процесса обновления до Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Обзор того, что необходимо сделать для обновления Project Server 2013 до Project Server 2016 <br/> |
|[Планирование обновления до Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Вопросы планирования обновления Project Server 2013 до Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Что нужно знать об обновлении до этой версии

Что необходимо знать об обновлении [Project Server 2016,](https://go.microsoft.com/fwlink/p/?linkid=841827) сообщает о некоторых важных изменениях обновления для этой версии, в том числе:
  
- При создании среды Project Server 2016, в которую будут перенесены данные Project Server 2013, установонные файлы Project Server 2016 включаются в SharePoint Server 2016. Дополнительные сведения [см. в подпроекте "Развертывание Project Server 2016".](https://go.microsoft.com/fwlink/p/?linkid=841829)
    
- Планы использования ресурсов в Project Server 2016 являются неподготовленными. Планы использования ресурсов Project Server 2013 будут перенесены в project Server 2016 и Project Online. Дополнительные [сведения см. в обзоре.](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 
    
## <a name="migrate-from-portfolio-server-2007"></a>Миграция с Portfolio Server 2007

Project Portfolio Server 2007 использовался вместе с Project Server 2007 для стратегии, приоритетов и оптимизации портфеля. После этой версии дополнительные версии Project Portfolio Server не создавались. Однако функции управления портфелями доступны в Project Server 2016 и версии Project Online premium. Но данные из Project Portfolio Server 2007 нельзя перенести в любой из этих проектов. Такие данные, как бизнес-драйверы, необходимо воссоздать.
  
Другие ресурсы
  
- [Описание службы Project Online:](https://go.microsoft.com/fwlink/p/?linkid=841280) См. функции управления портфелями, включенные в Project Server 2016 и Project Online premium.
    
- [Microsoft Office project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Связанные статьи

[План действий после окончания поддержки SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Ресурсы по обновлению серверов и клиентов Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
