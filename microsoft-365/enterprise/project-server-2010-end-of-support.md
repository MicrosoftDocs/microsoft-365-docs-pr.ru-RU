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
ms.openlocfilehash: e20c8752b088b783f622fabf30302bbb8d4b8975
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696452"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>План действий после прекращения поддержки Project Server 2010

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Project Server 2010 дойдет до конца поддержки от **13 апреля 2021 г**. Эта дата была расширена с момента предыдущего срока поддержки 13 октября 2020 г. Если в настоящее время используется Project Server 2010, обратите внимание на то, что следующие связанные продукты имеют следующие даты:
  
| Продукт |Дата окончания поддержки|
|:-----|:-----|
|Project 2010 Стандартный <br/> |13 октября 2020 г.  <br/> |
|Project 2010 профессиональный  <br/> |13 октября 2020 г.  <br/> |

   
Дополнительные сведения о серверах Office 2010, достигнутых в конце поддержки, можно найти [в статье обновление с серверов и клиентских продуктов office 2010](plan-upgrade-previous-versions-office.md).
  
## <a name="what-does-end-of-support-mean"></a>Что означает окончание поддержки?

Project Server, как и почти все продукты Майкрософт, имеет жизненный цикл поддержки, в котором мы предоставляем новые функции, исправления ошибок и обновления для системы безопасности. Этот жизненный цикл обычно продолжается в течение 10 лет с даты первоначального выпуска продукта, а окончание этого жизненного цикла называется окончанием поддержки продукта. Когда Project Server 2010 достиг конца поддержки 13 апреля 2021, корпорация Майкрософт больше не будет предоставлять следующее:
  
- Техническая поддержка проблем, которые могут возникнуть.
    
- Исправление ошибок для обнаруженных проблем, которые могут повлиять на стабильность и удобство использования сервера.
    
- Исправления для системы безопасности уязвимостей, которые могут привести к уязвимости сервера при нарушении безопасности.
    
- Обновления часового пояса.
    
Установка Project Server 2010 продолжит работу после этой даты. Однако из-за перечисленных выше изменений настоятельно рекомендуется выполнить миграцию из Project Server 2010 как можно скорее.
  
## <a name="what-are-my-options"></a>Что такое параметры?

Если вы используете Project Server 2010, необходимо ознакомиться с параметрами миграции, которые перечислены ниже.
  
- Миграция в Project Online
    
- Переход на более новую локальную версию Project Server (желательно Project Server 2019).

Ниже приведены два пути, которые можно использовать, чтобы избежать завершения поддержки Project Server 2010.

![Пути обновления Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

    


|**Зачем переходить на Project Server 2019?**|**Зачем нужна миграция в Project Online?**|
|:-----|:-----|
|Бизнес-правила ограничивают меня рабочими моими предприятиями в облаке.  <br/>  Мне нужно управлять обновлениями в моей среде.  <br/> | У меня есть мобильные или удаленные пользователи.  <br/>  Затраты на миграцию локальных серверов значительно важнее (оборудование, программное обеспечение, часы и усилия для реализации и т. д.).  <br/>  После миграции затраты на поддержание среды очень важны (например, автоматическое обновление, гарантированное время работы и т. д.).  <br/>  |

   
> [!NOTE]
> Для получения дополнительных сведений о возможностях перехода с серверов Office 2010, ознакомьтесь со статьей [ресурсы, которые помогут вам выполнить обновление серверов и клиентов office 2010](upgrade-from-office-2010-servers-and-products.md). Обратите внимание, что Project Server не поддерживает гибридную конфигурацию, так как Project Server и Project Online не могут совместно использовать один пул ресурсов. 

### <a name="what-are-my-options-for-project-client"></a>Что такое параметры для клиента Project?
Если вы используете Project профессиональный 2010 или Project стандартный 2010 и хотите изучить варианты миграции, вы можете выбрать:
- Переход на новую версию Project профессиональный или Project Стандартный.
- Переход к сетевому решению, такому как Project Online или Project для Интернета.
 
#### <a name="moving-to-a-newer-version-of-project-client"></a>Переход на новую версию клиента Project

Если вы выполняете миграцию из Project стандартный 2010, вы можете перейти на новую версию Project Standard (Project Стандартный 2016 или Project Стандартный 2019).  Мы рекомендуем перейти к последней версии, чтобы воспользоваться преимуществами новейших функций и функций. Кроме того, миграция на более меньшую версию (Project Standard 2016) означает, что вам потребуется выполнить миграцию с этой версии рано, когда отдается срок ее завершения.

Аналогично, если вы переходите с Project профессиональный 2010, вы можете перейти на новую версию (Project профессиональный 2019 или Project профессиональный 2016). Рекомендуем переместиться на последнюю версию, если это возможно.  Если вы используете Project профессиональный для подключения к Project Server, убедитесь, что вы выполняете миграцию на версию Project Professional, которая поддерживается для подключения к используемой версии Project Server.

Пользователи Project профессиональный 2010 также могут переходить на клиент Project Online для настольных ПК. Это версия Project профессиональный 2019 на основе подписки, которая включена в план подписки на проект 3 и проект план 5. 

#### <a name="moving-to-an-online-solution"></a>Переход к сетевому решению

Вы также можете выполнить миграцию из Project профессиональный 2010 или Project стандартный 2010 в интерактивные решения, основанные на подписках Project. В планах Project (план 3) и план 5 входит Project Online и Последнее облачное предложение, [Project для Интернета](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Оба предоставляют ряд новых функций и преимуществ, которые стоит рассмотреть.

Для получения дополнительных сведений о функциях, включенных в обе, а также о планах проектов, в которых они включены, ознакомьтесь с разделом [Описание службы Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).



  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>Важные замечания, которые необходимо принять во время планирования миграции из Project Server 2010

При планировании миграции из Project Server 2010 необходимо учитывать следующие рекомендации.
  
- **Получение помощи от поставщика решений Майкрософт** — обновление с Project Server 2010 может быть сложной задачей и требует значительных усилий по подготовке и планированию. Это может быть особенно сложным, если вы не использовались для настройки и первоначально настроили Project Server 2010. К счастью, у вас есть поставщики решений Майкрософт, которые могут сделать это, если вы планируете переход на Project Server 2019 или Project Online. Вы можете найти поставщика решений Майкрософт, который поможет вам выполнить миграцию в [центре поставщиков решений Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=841249). 
    
- **Запланируйте настройки** , имейте в виду, что многие настройки, работающие в среде project Server 2010, могут не работать при переходе на project Server 2019 или Project Online. В архитектуре Project Server существуют существенные различия между версиями, а также операционные системы, серверы баз данных и клиентские веб-браузеры, которые поддерживают работу с более новой версией. Составьте план, чтобы проверить или перестроить настройки по мере необходимости в новой среде. При планировании обновления также будет полезно проверить, действительно ли требуется определенная настройка при переходе вперед. [Создайте план для текущих настроек во время обновления до SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) содержит общие сведения об оценке и планировании текущих настроек при обновлении. 
    
- При планировании, выполнении и тестировании обновления **время и терпение** занимают много времени и сил, особенно при обновлении до Project Server 2019. Например, при переносе из Project Server 2010 в Project Server 2019 необходимо выполнить миграцию из Project Server 2010 в Project Server 2013, а затем проверить данные, а затем выполнить те же действия при переходе к каждой последующей версии (в Project Server 2016, а затем в Project Server 2019). Вы можете узнать у поставщика решений Майкрософт, что нужно сравнить предполагаемые затраты с оценками того, сколько времени потребуется для их выполнения, а также в каких затратах. 
    
## <a name="migrate-to-project-online"></a>Миграция в Project Online

Если вы решили выполнить миграцию из Project Server 2010 в Project Online, можно выполнить следующие действия, чтобы вручную перенести данные плана проекта:
  
1. Сохраните планы проекта из Project Server 2010. Формат MPP.
    
2. Используя Project профессиональный 2016, Project профессиональный 2019 или клиент Project Online для настольных ПК, откройте каждый MPP-файл, а затем сохраните и опубликуйте его в Project Online.
    
Вы можете вручную создать конфигурацию PWA в Project Online (например, создать все необходимые настраиваемые поля или корпоративные календари). Кроме того, вы можете помочь поставщикам решений Майкрософт.
  
Основные ресурсы:
  
|**Ресурс**|**Описание**|
|:-----|:-----|
|[Начало работы с Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Настройка и использование Project Online.  <br/> |
|[Описание службы Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Сведения о различных доступных планах Project Online.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Переход на новую локальную версию Project Server

Несмотря на то, что вы уверены, что вы можете добиться наилучшего качества и удобства работы пользователей, переполнив их в Project Online, мы также понимаем, что в некоторых организациях необходимо хранить данные проекта в локальной среде. Если вы решили хранить данные проекта локально, вы можете перенести среду Project Server 2010 в Project Server 2013, Project Server 2016 или Project Server 2019.
  
Рекомендуется выполнить миграцию в Project Server 2019, если вы не можете выполнить миграцию в Project Online. Project Server 2019 включает в себя большинство основных функций и улучшений, включенных в предыдущие выпуски Project Server, и наиболее полно соответствует интерфейсу, доступному в Project Online (хотя некоторые функции доступны только в Project Online).
  
После завершения каждой миграции необходимо проверить данные, чтобы убедиться, что они успешно перенесены.
  
> [!NOTE]
> Если вы планируете переход на Project Server 2013 только в том случае, если вы ограничены локальным решением, то важно отметить, что осталось только еще несколько лет поддержки. Дата окончания поддержки Project Server 2013 с пакетом обновления 2 (SP2) — 10/13/2023. Для получения дополнительных сведений о конце дат поддержки обратитесь к разделу [Политика жизненного цикла продуктов Майкрософт](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2019"></a>Как перейти к Project Server 2019?

Различия в архитектуре Project Server 2010 и Project Server 2019 запрещают прямой путь миграции. Это означает, что после обновления до Project Server 2019 вам потребуется перенести данные Project Server 2010 в следующую последующую версию Project Server.
  
Чтобы обновить Project Server 2010 до Project Server 2019, выполните следующие действия:
  
1. Переход на Project Server 2013.
    
2. Миграция из Project обслуживает 2013 в Project Server 2016.
    
3. Миграция из Project Server 2016 в Project Server 2019.
    
После завершения каждой миграции необходимо проверить данные, чтобы убедиться, что они успешно перенесены.
  
    
### <a name="step-1-migrate-to-project-server-2013"></a>Шаг 1: миграция на Project Server 2013

Первым этапом переноса данных Project Server 2010 в Project Server 2019 является предварительная миграция в Project Server 2013. 
  
Полное представление о том, что необходимо сделать для обновления Project Server 2010 до Project Server 2013, приведено в статье [Upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Основные ресурсы:
  
- [Обзор этапов обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2010 до Project Server 2013.
- [Планирование обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) 

  Изучите рекомендации по планированию, которые необходимо выполнить при обновлении Project Server 2010 до Project Server 2013, включая требования к системе.
   
[Что нового в Project Server 2013 Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) сообщает о важных изменениях для обновления этой версии, что наиболее заметно: 
  
- Обновление на месте до Project Server 2013 отсутствует. Метод с присоединением базы данных — единственный поддерживаемый метод обновления с Project Server 2010 до Project Server 2013.
    
- Процесс обновления не только преобразует данные Project Server 2010 в формат Project Server 2013, но также объединяет четыре базы данных Project Server 2010 в одну базу данных Project Web App.
    
- SharePoint Server 2013 и Project Server 2013 изменились на проверку подлинности на основе утверждений из предыдущей версии. При использовании классической проверки подлинности необходимо принять во внимание рекомендации по обновлению. Дополнительные сведения см. в статье [Migrate from classic-mode to claims-based authentication in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).
    
Основные ресурсы:
  
- [Общие сведения о процессе обновления до Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Обновление баз данных и семейств веб-сайтов Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Схема процесса обновления Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Отличная консолидация баз данных, Project Server 2010 – 2013 миграция на 8 простых действий](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-2-migrate-to-project-server-2016"></a>Шаг 2: миграция на Project Server 2016

После перехода на Project Server 2013 и проверки того, что данные успешно перенесены, следующим шагом является перенос данных в Project Server 2016.
  
Полное представление о том, что необходимо сделать для обновления Project Server 2013 до Project Server 2016, приведено в статье [Upgrade to Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).
  
Основные ресурсы:
  
- [Обзор процесса обновления до Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Изучите рекомендации по планированию, которые необходимо выполнить при обновлении Project Server 2013 до Project Server 2016.
   
Что нужно [знать о Project Server 2016 Upgrade](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) содержит некоторые важные изменения для обновления до этой версии, в том числе: 
  
- При создании среды Project Server 2016, в которую будут перенесены данные Project Server 2013, обратите внимание на то, что установочные файлы Project Server 2016 включены в SharePoint Server 2016. Дополнительные сведения см. в статье [deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Планы ресурсов являются устаревшими в Project Server 2016. Планы ресурсов Project Server 2013 будут перенесены в задействование ресурсов в Project Server 2016 и Project Online. Для получения дополнительных сведений см. [Обзор: задействование ресурсов](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
### <a name="step-3-migrate-to-project-server-2019"></a>Шаг 3: миграция на Project Server 2019

После перехода на Project Server 2016 и проверки того, что данные успешно перенесены, следующим шагом является перенос данных в Project Server 2019.
  
Полное представление о том, что необходимо сделать для обновления Project Server 2016 до Project Server 2019, приведено в статье [Upgrade to Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).
  
Основные ресурсы:
  
- [Обзор процесса обновления Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Получите высокоуровневое представление о том, что нужно сделать для обновления с Project Server 2013 до Project Server 2016.

- [Планирование обновления до Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Изучите рекомендации по планированию, которые необходимо выполнить при обновлении Project Server 2016 до Project Server 2019.
   
Что нужно [знать о Project Server 2019 Upgrade](https://go.microsoft.com/fwlink/p/?linkid=841827) содержит некоторые важные изменения для обновления до этой версии, в том числе: 
  
- В процессе обновления данные из базы данных Project Server 2016 будут перенесены в базу данных контента SharePoint Server 2019.  Project Server 2019 больше не будет создавать собственную базу данных Project Server в ферме SharePoint Server.

- После обновления следует учитывать несколько изменений в Project Web App.  Описание этих возможностей приведено в статье [новые возможности Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

  
Другие ресурсы
  
- [Описания служб Project Online](https://go.microsoft.com/fwlink/p/?linkid=841280): сведения о функциях управления портфелем, включенных в project Server 2016 и Project Online Premium.
    
- [Руководство по миграции Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Обзор параметров для клиентов и серверов Office 2010 и Windows 7

Визуальное представление возможностей обновления, миграции и перехода на облачные решения для клиентов и серверов Office 2010, а также Windows 7 см. на плакате [Прекращение поддержки](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Изображение плаката "Прекращение поддержки клиентов и серверов Office 2010 и Windows 7"](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Этот одностраничный плакат поможет быстро ознакомиться с различными методами, которые можно использовать, чтобы предотвратить прекращение поддержки клиентских и серверных продуктов Office 2010 и Windows 7. В нем указаны предпочтительные методы и возможности поддержки в Microsoft 365 корпоративный.

Вы также можете [скачать](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) этот плакат и распечатать его в формате письма, юридического документа или газетном формате (11 х 17).
   
## <a name="related-topics"></a>Связанные статьи

[Переход с SharePoint 2010](upgrade-from-sharepoint-2010.md)
  
[Обновление серверов и клиентов Office 2010](upgrade-from-office-2010-servers-and-products.md)
  

