---
title: План действий после прекращения поддержки PerformancePoint Server 2007.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007, ProClarity и SharePoint Server 2007 достигли конца поддержки. Ознакомьтесь с этой статьей, чтобы спланировать обновление решения bi.
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927340"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>План действий после прекращения поддержки PerformancePoint Server 2007.

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Серверы и приложения Office 2007 достигли конца поддержки, включая серверы и приложения, которые можно использовать в рамках решений бизнес-аналитики (BI). В следующей таблице перечислены затронутые bi-приложения:
  
|**Приложения Microsoft BI**|**Поддержка дат завершена**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Пакет обновления 3  <br/> Профессиональный настольный компьютер ProClarity 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |11 июля 2017 г.  <br/> |
|SharePoint Server 2007 Пакет обновления 3  <br/> |10 октября 2017 г.  <br/> |
|PerformancePoint Server 2007 Пакет обновления 3  <br/> |9 января 2018 г.  <br/> |
   
Дополнительные сведения см. в справке Ресурсы, которые помогут обновить серверы и клиенты [Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-does-end-of-support-mean"></a>Что означает *конец поддержки?*

Как и большинство продуктов Майкрософт, PerformancePoint Server 2007 sp3, программное обеспечение ProClarity и SharePoint Server 2007 SP3 имеют жизненный цикл поддержки, в ходе которого Корпорация Майкрософт предоставляет новые функции, исправления ошибок и обновления безопасности. Жизненный цикл продукта обычно длится 10 лет с начального выпуска продукта. Конец жизненного цикла называется завершением поддержки продукта. Поскольку proClarity, PerformancePoint Server и SharePoint Server 2007 достигли конца поддержки, Microsoft больше не предоставляет:
  
- Техническая поддержка проблем, которые могут возникнуть.
    
- Исправление ошибок для обнаруженных проблем, которые могут повлиять на стабильность и доступность серверов.
    
- Исправления безопасности для обнаруженных уязвимостей, которые могут сделать серверы или приложения уязвимыми для нарушений безопасности.
    
- Обновления часовой зоны.
    
Установка ProClarity, SharePoint Server 2007 SP3 и PerformancePoint Server 2007 SP3 будет продолжать работать, даже если поддержка завершена. Однако настоятельно рекомендуется как можно скорее перейти из этих приложений.
  
## <a name="what-are-my-options"></a>Какие у меня варианты?

С 2007 г. в приложениях Microsoft BI было много изменений, и у вас есть несколько вариантов, которые необходимо рассмотреть, как по сумме в следующей таблице.
  
|**Если вы использовали это ...**|**Изучите эти параметры ...**|**И имейте это в виду ...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 г. возможности аналитики мониторинга, в том &amp; числе:<br/>- Сервер мониторинга PerformancePoint <br/>- Конструктор панели мониторинга PerformancePoint<br/>- Панель мониторинга просмотра для SharePoint Services (используется для отрисовки панелей мониторинга PerformancePoint, показателей и отчетов)<br/> |**Excel с Excel в браузере** (в облаке или локальном). Обзор см. в [обзоре возможностей BI в Excel и Microsoft 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)<br/><br/> **Power BI** (в облаке или локальном помещении). Обзор см. в [обзоре "Что такое Power BI"?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server службы отчетности** (локально). Обзор см. в SQL Server службы отчетов [(SSRS): Создание,](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)развертывание и управление мобильными и paginated отчетами. <br/><br/> **PerformancePoint Services** (локально). Обзор см. в раздел Что нового [для PerformancePoint Services (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14)) <br/> |Excel доступен как сетевое (облачное) или локальное решение. Многие потребности в отчетах и панели мониторинга можно удовлетворены с помощью Excel.  <br/><br/> Power BI доступен в качестве сетевого или локального решения. Power BI не входит в Microsoft 365. Но вы можете начать использовать Power BI бесплатно. Позже, в зависимости от использования данных и бизнес-потребностей, вы можете перейти на Power BI Pro с Помощью Microsoft 365 E5.<br/> <br/> Службы отчетов и PerformancePoint Services — это локальное решение. <br/><br/> PerformancePoint Services sharePoint Server 2010, SharePoint Server 2013 и SharePoint Server 2016. <br/> <br/> Некоторые функции и типы отчетов, доступные в PerformancePoint Server 2007 г., недоступны в Excel, Power BI, Reporting Services или PerformancePoint Services. Просмотрите доступные функции, чтобы определить наилучшее решение для бизнес-потребностей. <br/> |
| Программное обеспечение ProClarity, в том числе:<br/>- Профессиональный настольный компьютер ProClarity<br/> - Сервер аналитики ProClarity<br/>- ProClarity SharePoint Viewer<br/> |**Работайте с партнером Майкрософт,** чтобы определить решение, которое наилучшим образом отвечает вашим потребностям. Посетите [Центр партнеров Майкрософт.](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> Вы также можете использовать Excel с Excel в браузере, Power BI, SQL Server службы отчетности или PerformancePoint Services.  <br/> |Некоторые, но не все функции программного обеспечения ProClarity доступны в других предложениях Майкрософт, включая Excel, Power BI, Reporting Services и PerformancePoint Services.  <br/> |
|KPIs SharePoint Server 2007 (также называемые KPIs MOSS)  <br/> |**Excel с службы Excel**. Обзор см. в [разделе Бизнес-аналитика в Excel и службы Excel (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |KPIs MOSS, созданные с помощью SharePoint Server 2007, можно использовать в SharePoint Server 2010, SharePoint Server 2013 и SharePoint Server 2016. Но вы не можете создать новые KPIs MOSS.  <br/> |
|Excel 2007  <br/> |**Excel** (в облаке или локальном помещении). Обзор см. в [обзоре возможностей BI в Excel и Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI** (в облаке или локальном помещении). Обзор см. в [обзоре "Что такое Power BI"?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |И Excel, и Power BI предлагают облачные и локальное решения организации с поддержкой широкого спектра источников данных.  <br/> |
   
### <a name="help-selecting-a-solution"></a>Помощь в выборе решения

С таким количеством доступных вариантов bi может показаться, что определение наиболее оптимальных вариантов может показаться подавляющим. У нас есть руководство по интернету, чтобы помочь. См. [в подборе инструментов microsoft Business Intelligence (BI) для анализа и отчетности.](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)
  
### <a name="what-if-i-dont-upgrade-now"></a>Что делать, если я не обновить сейчас?

Вы можете не обновляться немедленно. Существующие серверы и приложения будут продолжать работать. Но дополнительные обновления, включая обновления безопасности, не будут получаться, так как поддержка завершена. И если что-то пойдет не так с серверными приложениями, вы не сможете получить помощь от технической поддержки Майкрософт.
  
## <a name="how-do-i-plan-my-upgrade"></a>Как планировать обновление?

После изучения параметров обновления следующий шаг — подготовка плана обновления. В следующих разделах содержатся сведения и дополнительные ресурсы. У вас есть четыре основных параметра, в том числе два, которые работают как в облаке, так и на локальном сайте, а два — только для локального параметров:
  
|**Option**|**В облаке или на месте?**|
|:-----|:-----|
|[Excel с SharePoint Server (локально)](#excel-with-sharepoint-server-on-premises) <br/> |Оба  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Оба  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |Только на месте  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |Только на месте  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Использование Excel (в облаке или локальном помещении)

С помощью Excel, который  также службы Excel в SharePoint Server, вы можете просматривать и использовать книги в окне браузера, даже если Excel не установлен на компьютере. Вы можете использовать Excel для создания отчетов, показателей и панелей мониторинга. Затем поделитесь своими книгами с другими людьми, которые могут использовать Excel в браузере, независимо от того, используют ли они SharePoint Online в рамках локальной microsoft 365 или SharePoint Server. Можно использовать данные, хранимые на локальной основе или в облаке, что позволяет использовать самые разнообразные источники данных.
  
В следующей таблице сравнивают ключевые преимущества использования Excel с Microsoft 365 с использованием Excel с SharePoint Server. Дополнительные сведения.
  
|**Excel с Microsoft 365 (в облаке)**|**Excel с SharePoint Server (локально)**|
|:-----|:-----|
|**Вы получаете последнюю, наибольшую версию Excel**. В Microsoft 365 вы получаете последнюю версию Excel, которая включает новые мощные типы диаграмм, возможность создания диаграмм и таблиц быстро и легко, а также поддержку дополнительных источников данных. <br/> <br/> **Настройка намного проще**. Excel включен в Microsoft 365 для бизнеса, поэтому с вашей стороны не требуется никаких тяжелых подтяжок. Зарегистрироваться и войти, и вы будете работать быстрее и эффективнее, чем при обновлении локального сервера. <br/> <br/> **Люди имеют везде доступ к своим книгам**. Люди могут безопасно просматривать книги, где бы они ни были, с помощью компьютера, смартфона и планшета. <br/> <br/> **Там больше!** См. [возможности BI в Excel и Office 365.](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**Вы управляете глобальными настройками.** В качестве администратора SharePoint можно указать глобальные параметры, такие как безопасность, балансировка нагрузки, управление сеансами, кэширование книг и внешние подключения к данным. <br/> <br/> **Вы можете использовать службы Excel с PerformancePoint Services**. Вы можете настроить службы Excel и PerformancePoint Services в рамках установки SharePoint Server и включить отчеты службы Excel в панели мониторинга PerformancePoint. <br/> <br/> **Там больше!** Сведения о бизнесе см. в [excel и службы Excel (SharePoint Server 2013).](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Excel с Microsoft 365 (в облаке)

При переходе в Microsoft 365 у вас будут самые последние службы и приложения, включая Excel 2016. PerformancePoint Services microsoft 365 недоступна, поэтому вы замените содержимое панели мониторинга PerformancePoint книгами Excel или другими отчетами. Хорошая новость заключается в том, что в Excel 2016 имеется множество новых типов диаграмм, и создавать впечатляющие панели мониторинга в Excel проще, чем когда-либо. И регулярно добавляются новые функции. Дополнительные дополнительные возможности см. в дополнительных подробной информации о новых [версиях Excel 2016 для Windows.](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)
  
Кроме того, если вы покупаете 50 или более мест в Microsoft 365, команда Microsoft FastTrack поможет вам настроиться. Дополнительные дополнительные информации можно найти в [FastTrack.](https://www.microsoft.com/fasttrack/microsoft-365)
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel с SharePoint Server (локально)

При обновлении до более новой версии SharePoint можно использовать Excel с службы Excel или в браузере следующим образом:
  
- службы Excel SharePoint Server 2010
    
- Службы Excel в SharePoint Server 2013
    
- Excel, который является частью Office Online Server, установлен отдельно от SharePoint Server 2016
    
Вы можете настроить PerformancePoint Services в новой версии SharePoint Server, а также использовать его вместе с Excel.
  
Дополнительные информацию о параметрах обновления SharePoint см. в [разделе SharePoint Server 2007 end of support Roadmap.](sharepoint-2007-end-of-support.md)
  
Дополнительные сведения о службы Excel см. [в службы Excel (SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Использование Power BI (в облаке или локальном помещении)

Power BI — это набор средств бизнес-аналитики для анализа данных и обмена сведениями. С помощью Power BI можно использовать локальное или сетевое источники данных для создания интерактивных отчетов и панелей мониторинга. Люди могут просматривать и использовать отчеты и панели мониторинга на своих компьютерах или мобильных устройствах.
  
Power BI не является частью Microsoft 365 или SharePoint Server. Это отдельное предложение, которое включает power BI Desktop, шлюзы Power BI и службу Power BI. Power BI также интегрируется с SharePoint Online. Вы можете начать работу с Power BI бесплатно. С учетом использования данных и бизнес-потребностей можно позже перейти на Power BI Pro с помощью Microsoft 365 E5. Дополнительные дополнительные информации см. [в дополнительных подробной информации о том, что такое Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>Использование служб отчетности (локально)

SQL Server службы отчетности предоставляют надежное решение для отчетности. Вы можете настроить службы отчетности в родном или интегрированном режиме SharePoint. Для авторских отчетов можно использовать несколько различных средств, в том числе конструктор отчетов, построитель отчетов и Power View. С последним выпуском SQL Server вы также можете использовать SQL Server Mobile Report Publisher для доставки отчетов, масштабирования до любого размера экрана. Это позволяет пользователям потреблять отчеты на своих мобильных устройствах. Дополнительные данные см. в SQL Server службы отчетов [(SSRS): Создание,](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)развертывание и управление мобильными и paginated отчетами.
  
### <a name="use-performancepoint-services-on-premises"></a>Использование PerformancePoint Services (локально)

PerformancePoint Server 2007 был продан отдельно от SharePoint Server 2007. Начиная с SharePoint Server 2010, PerformancePoint Services является приложением-службой в SharePoint Server. Поэтому для использования PerformancePoint Services не нужно приобретать отдельные лицензии сервера или оборудование.
  
Чтобы перейти PerformancePoint Server 2007 PerformancePoint Services, переходить к более последней версии SharePoint Server и настраивать PerformancePoint Services. Версия SharePoint Server, которую вы перемещали, определяет, можно ли импортировать существующий контент панели мониторинга с PerformancePoint Server 2007 г. PerformancePoint Services.
  
- При обновлении до SharePoint Server 2010 вы можете импортировать содержимое панели мониторинга PerformancePoint с PerformancePoint Server 2007 г. до PerformancePoint Services в SharePoint Server 2010. Дополнительные материалы см. в [раздел Import Wizard: PerformancePoint Server 2007 года в SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14)).
    
- При переходе на SharePoint Server 2013 или SharePoint Server 2016 вам, скорее всего, потребуется создать новый контент панели мониторинга (источники данных, отчеты, системы показателей и страницы панели мониторинга).
    
Чтобы начать работу с PerformancePoint Services плана обновления, см. в следующих ресурсах:
  
- [Конец плана поддержки SharePoint Server 2007](sharepoint-2007-end-of-support.md)
    
- Когда вы знаете, в какую версию SharePoint вы переходите, см. соответствующую статью для PerformancePoint Services:
    
  - [Планирование PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [PerformancePoint Services в обзоре SharePoint Server 2013](/sharepoint/administration/performancepoint-services-overview)
    
  - [Обзор служб PerformancePoint Services в SharePoint Server 2016](/sharepoint/administration/performancepoint-services-overview)
    
При обновлении до PerformancePoint Services вы получите несколько новых функций и улучшений. PerformancePoint Services предлагает улучшенные системы показателей; новые визуализации, такие как отчет о дереве разложения и сведениях о KPI; дополнительные типы диаграмм; улучшение возможностей фильтрации time Intelligence; и улучшение соответствия требованиям доступности. Дополнительные дополнительные возможности см. в PerformancePoint Services [(SharePoint Server 2010).](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>Где можно получить помощь в обновлении?

Независимо от того, обновляете ли вы локальное обновление или перейдете в Microsoft 365, рекомендуется работать с партнером Майкрософт. Квалифицированный партнер может помочь вам определить решение, которое наилучшим образом отвечает вашим бизнес-потребностям, и помочь с развертыванием. Посетите [Центр партнеров Майкрософт](https://go.microsoft.com/fwlink/?linkid=841249)и используйте фильтры поиска для поиска поставщика решений.
  
## <a name="related-topics"></a>Родственные темы

[Ресурсы, которые помогут обновить серверы и клиенты Office 2007](upgrade-from-office-2007-servers-and-products.md)