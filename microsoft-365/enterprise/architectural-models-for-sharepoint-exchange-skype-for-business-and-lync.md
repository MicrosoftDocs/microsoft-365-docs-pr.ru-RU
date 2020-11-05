---
title: Архитектурные модели для SharePoint, Exchange, Skype для бизнеса и Lync
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: Получите плакаты, описывающие архитектурные модели, развертывание и параметры платформы для SharePoint, Exchange, Skype для бизнеса и Lync.
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919824"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Архитектурные модели для SharePoint, Exchange, Skype для бизнеса и Lync

В этой статье плакаты по ИТ описывают архитектурные модели и варианты развертывания SharePoint, Exchange, Skype для бизнеса и Lync. Они также предоставляют сведения о проектировании для развертывания SharePoint в Microsoft Azure.
  
С помощью Microsoft 365 вы можете предоставить знакомые службы совместной работы и общения через облако. При наличии нескольких исключений пользователь работает так же, как при локальном развертывании, так и с помощью Microsoft 365. 

Этот унифицированный пользовательский интерфейс усложняет решение о том, где следует располагать каждую рабочую нагрузку. Кроме того, возникают вопросы:
  
- Как выбрать платформу для отдельных рабочих нагрузок?
    
- Имеет ли смысл оставлять какую-либо службу локальной?
    
- В каком сценарии требуется гибридное развертывание?
    
- Как Azure помещается в изображение?
    
- Какие конфигурации рабочих нагрузок Office Server поддерживает Azure?
    
> [!TIP]
> Большинство афиш в этой статье доступны на нескольких языках. Доступные языки: китайский, английский, французский, немецкий, итальянский, японский, корейский, португальский, русский и испанский. Чтобы скачать афишу на одном из этих языков, в миниатюрном изображении афиши выберите пункт **Дополнительные языки**.
  
Сообщите нам о том, что вы думаете! Отправьте нам сообщение по адресу [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Используйте следующие ссылки, чтобы получить плакаты, которые вам нужны:
  
- **Архитектурные модели** : Используйте эти ресурсы, чтобы определить идеальную платформу и конфигурацию для SharePoint 2016 и Skype для бизнеса 2015.
    
  - [Архитектурные модели Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Базы данных SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Архитектурные модели Microsoft Skype для бизнеса 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Платформа** : Используйте эти ресурсы, чтобы определить идеальную платформу и конфигурацию для SharePoint 2013, Exchange 2013 и Lync 2013.
    
  - [Варианты платформы SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Варианты платформы Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Варианты платформы Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint server 2013 в Azure** : Используйте эти плакаты для создания и настройки рабочих нагрузок SharePoint Server 2013 в службах инфраструктуры Azure.
    
  - [Веб-сайты в Azure с использованием SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Пример проекта: веб-сайты в Azure для SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Аварийное восстановление SharePoint в Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Афиши с архитектурными моделями

Плакаты по ИТ для SharePoint 2016 и Skype для бизнеса 2015 предоставляют способ сравнить методы развертывания в удобном для печати формате. Афиши список всех параметров конфигурации или платформы. Они предоставляют следующие сведения для каждого параметра:
  
- **Обзор** : краткое описание платформы, включая концептуальную схему.
    
- **Лучше всего подходит для** : распространенные сценарии, идеально подходящие для платформы.
    
- **Требования к лицензированию** : лицензии, необходимые для развертывания.
    
- **Задачи архитектуры** : решения, которые необходимо принять в качестве архитектора.
    
- **Задачи и обязанности ИТ-специалистов** : ежедневные обязанности ИТ-специалистов, которые необходимо спланировать.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Архитектурные модели Microsoft SharePoint Server 2016

|Item|Описание|
|---|---|
|[![Эскиз плаката для архитектурных моделей SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=52650)|На этой афише ИТ описываются локальные конфигурации SharePoint Online, Azure и SharePoint, о которых необходимо знать для лиц, принимающих бизнес-решения и архитекторов решений. <br/><br/> - **SharePoint Online (SaaS)** : использование SharePoint через программное обеспечение как модель подписки на программное обеспечение (SaaS). <br/> - **Гибридная среда SharePoint** : Перенесите сайты и приложения SharePoint в облако в удобном для вас темпе. <br/> - **SharePoint в Azure (IaaS)** : Расширьте локальную среду до Azure и развертывайте серверы SharePoint 2016. (Эта модель рекомендуется для сред с высоким уровнем доступности и аварийного восстановления, а также сред разработки и тестирования.) <br/> - **Локальная среда SharePoint** : планирование, развертывание, Обслуживание и настройка среды SharePoint в обслуживаемом центре обработки данных.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Базы данных SharePoint Server 2016

|Item|Описание|
|---|---|
|[![Эскиз афиши баз данных SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=55041)|Эта Афиша ИТ является кратким справочником по базам данных SharePoint Server 2016. Вы увидите сведения для каждой базы данных: <br/><br/> - Размер <br/> - Рекомендации по масштабированию <br/> - Особенности ввода-вывода <br/> - Требования <br/><br/>  На первой странице показаны системные базы данных SharePoint и приложения-службы с несколькими базами данных. На второй странице представлены сведения о приложениях служб с одной базой данных. <br/><br/>  Дополнительные сведения см. [в статье типы и описания баз данных в SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions).|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Архитектурные модели Microsoft Skype для бизнеса 2015

|Item|Описание|
|---|---|
|[![Эскиз плаката для архитектурных моделей Skype для бизнеса.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=55022)|На этом плакате описывается Skype для бизнеса Online, локальная, гибридная и облачная УАТС. Здесь также описывается интеграция с конфигурациями Exchange и SharePoint, о которых необходимо знать для лиц, принимающих бизнес-решения, и архитекторов решений. <br/><br/> Плакат предназначен для ИТ-специалистов, которые позволяют ИТ-специалистам создавать сведения об основных архитектурных моделях, с помощью которых можно использовать Skype для бизнеса Online и локальную среду Skype для бизнеса. <br/><br/>Начните с настройки, которая наилучшим образом подходит потребностям и планам Организации. При необходимости учитывайте и используйте другие настройки. Например, вам может потребоваться интеграция с Exchange и SharePoint или решение, использующее преимущества облачной УАТС Майкрософт.|
   
## <a name="platform-options-posters"></a>Афиши с вариантами платформ

Плакаты для ИТ для SharePoint 2013, Exchange 2013 и Lync 2013 позволяют быстро сравнить методы развертывания. Каждый Афиша содержит список всех конфигураций или параметров платформы. Он предоставляет следующие сведения для каждого параметра:
  
- **Обзор** : краткое описание платформы, включая концептуальную схему.
    
- **Лучше всего подходит для** : распространенные сценарии, идеально подходящие для платформы.
    
- **Требования к лицензированию** : лицензии, необходимые для развертывания.
    
- **Задачи архитектуры** : решения, которые необходимо принять в качестве архитектора.
    
- **Задачи и обязанности ИТ-специалистов** : ежедневные обязанности ИТ-специалистов, которые необходимо спланировать.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Варианты платформы SharePoint 2013

|Item|Описание|
|---|---|
|[![Эскиз Афиши "варианты платформы SharePoint 2013".](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=40332)|Для лиц и архитекторов, принимающих деловые решения, на этом плакате показаны варианты платформы для SharePoint 2013, SharePoint в Microsoft 365, локальная гибридная среда с Microsoft 365, Azure и локальное развертывание. В нем представлены общие сведения о каждой архитектуре, рекомендациях, требованиях к лицензиям и списках архитекторов и ИТ-специалистов для каждой платформы. На плакате выделено несколько решений SharePoint в Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Варианты платформы Exchange 2013

|Item|Описание|
|---|---|
|[![Эскиз афиши с параметрами платформы Exchange.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=42676)|Для лиц и архитекторов, принимающих деловые решения, в этом афише описываются варианты платформы для Exchange 2013. Клиенты могут выбрать Exchange Online с помощью Microsoft 365, гибридного Exchange, локального сервера Exchange Server и размещенного Exchange. Афиша подробно описывает каждый вариант архитектуры, в том числе идеальные сценарии для каждого, требования к лицензии и обязанности ИТ-специалистов.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Варианты платформы Lync 2013

|Item|Описание|
|---|---|
|[![Эскиз Афиши "варианты платформы Lync 2013".](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41677)|Для лиц и архитекторов, принимающих деловые решения, в этом афише описываются варианты платформы для Lync 2013. Клиенты могут выбирать из Lync Online с помощью Microsoft 365, гибридной среды Lync, локальной среды Lync Server и размещенной Lync. В ИТ-афише описан каждый вариант архитектуры, в том числе идеальные сценарии для каждого, требования к лицензии и обязанности ИТ-специалистов.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Афиши с решениями SharePoint в Azure

Плакаты для ИТ для SharePoint в Azure содержат решения на основе Azure, использующие SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Веб-сайты в Microsoft Azure с использованием SharePoint Server 2013

|Item|Описание|
|---|---|
|[![Изображение сайтов Интернета в Azure с помощью афиши SharePoint Server 2013.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41992)|Этот плакат имеет основные действия по проектированию и рекомендованную архитектуру для веб-сайтов в Azure.  <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Веб-сайты в Azure с использованием SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Архитектуры Azure для SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Веб-сайты в Azure для SharePoint 2013

|Item|Описание|
|---|---|
|[![Изображение веб-сайтов в плакате Microsoft Azure для SharePoint Server 2013.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41991)|Используйте этот пример проектирования в качестве отправной точки для собственной архитектуры сайта в Интернете в Azure с помощью SharePoint Server 2013. <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Веб-сайты в Azure с использованием SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Архитектуры Azure для SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Аварийное восстановление SharePoint в Microsoft Azure

|Item|Описание|
|---|---|
|[![Изображение афиши для процесса аварийного восстановления SharePoint в Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41993)|На этой афише для ИТ-специалистов отображены принципы создания архитектуры для среды аварийного восстановления в Azure. <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Аварийное восстановление SharePoint Server 2013 в Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Архитектуры Azure для SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>См. также

- [Центр архитектуры и решений Microsoft 365](../solutions/solution-architecture-center.md)
  
- [Модели облачной архитектуры Майкрософт](../solutions/cloud-architecture-models.md)
  
- [Руководства по лаборатории тестирования Microsoft 365](m365-enterprise-test-lab-guides.md)
  
- [Гибридные решения](hybrid-solutions.md)

