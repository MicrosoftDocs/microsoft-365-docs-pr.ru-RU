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
description: Получите ИТ-плакаты с описанием архитектурных моделей, развертывания и платформы для SharePoint, Exchange, Skype для бизнеса и Lync.
ms.openlocfilehash: 6c8aea1f6389c5007adb1800639488972483d5fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905516"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Архитектурные модели для SharePoint, Exchange, Skype для бизнеса и Lync

Плакаты ИТ в этой статье описывают архитектурные модели и параметры развертывания для SharePoint, Exchange, Skype для бизнеса и Lync. Они также предоставляют сведения о разработке для развертывания SharePoint в Microsoft Azure.
  
Используя Microsoft 365, вы можете предоставлять знакомые службы совместной работы и связи через облако. За несколькими исключениями пользовательский интерфейс остается таким же, независимо от того, поддерживается ли локальное развертывание или используется Microsoft 365. 

Это единое пользовательское впечатление усложняет решение о том, где разместить каждую нагрузку. Кроме того, возникают вопросы:
  
- Как выбрать платформу для отдельных рабочих нагрузок?
    
- Имеет ли смысл оставлять какую-либо службу локальной?
    
- В каком сценарии подходит гибридное развертывание?
    
- Как Azure вписывается в изображение?
    
- Какие конфигурации рабочих Office серверов поддерживают Azure?
    
> [!TIP]
> Большинство плакатов в этой статье доступны на нескольких языках. Доступные языки включают китайский, английский, французский, немецкий, итальянский, японский, корейский, португальский, русский и испанский. Чтобы скачать плакат на одном из этих языков, под изображением эскиза плаката выберите **Дополнительные языки**.
  
Ждем ваших отзывов по адресу [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Чтобы получить нужные плакаты, используйте следующие ссылки:
  
- **Архитектурные** модели. Используйте эти ресурсы для определения идеальной платформы и конфигурации для SharePoint 2016 и Skype для бизнеса 2015.
    
  - [Архитектурные SharePoint Microsoft 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Базы данных Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Архитектурные Skype для бизнеса Microsoft 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Платформа.** Используйте эти ресурсы для определения идеальной платформы и конфигурации для SharePoint 2013, Exchange 2013 и Lync 2013.
    
  - [SharePoint 2013 г.](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 г.](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Параметры платформы Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013** в Azure: Используйте эти ИТ-плакаты для разработки и настройки рабочих нагрузок SharePoint Server 2013 в службах инфраструктуры Azure.
    
  - [Сайты Интернета в Azure с SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Пример дизайна: сайты в Azure для SharePoint 2013 г.](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint аварийного восстановления в Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Афиши с архитектурными моделями

ИТ-плакаты SharePoint 2016 и Skype для бизнеса 2015 г. предоставляют способ сравнения методов развертывания в удобном для печати формате. На плакатах перечисляют все параметры конфигурации или платформы. Они предоставляют следующую информацию для каждого варианта:
  
- **Обзор.** Краткое описание платформы, включая концептуальную схему.
    
- **Наиболее подходящие** для: распространенные сценарии, идеально подходящие для платформы.
    
- **Требования к лицензиям.** Лицензии, необходимые для развертывания.
    
- **Задачи архитектуры.** Решения, которые необходимо принять в качестве архитектора.
    
- **Задачи и обязанности** ИТ-специалистов. Ежедневные обязанности, которые необходимо планировать ИТ-сотрудникам.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Архитектурные модели Microsoft SharePoint Server 2016

|Item|Описание|
|---|---|
|[![Эскиз плаката SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=52650)|На этом плакате описывается SharePoint, Azure и SharePoint локальной конфигурации, о которую должны знать разработчики бизнес-решений и архитекторы решений. <br/><br/> - **SharePoint Online (SaaS)**: потреблять SharePoint с помощью программного обеспечения в качестве модели подписки на службу (SaaS). <br/> - **SharePoint** гибрид: перемещение SharePoint сайтов и приложений в облако в своем собственном темпе. <br/> - **SharePoint Azure (IaaS)**: Расширение локальной среды в Azure и развертывание SharePoint 2016 года. (Эта модель рекомендуется для сред с высокой доступностью или аварийного восстановления и среды разработчика и тестирования.) <br/> - **SharePoint** локальной среде: планирование, развертывание, обслуживание и настройка SharePoint среды в поддерживаемом вами центре обработки данных.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Базы данных SharePoint Server 2016

|Item|Описание|
|---|---|
|[![Эскиз плаката SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=55041)|Этот ИТ-плакат является быстрой ссылкой для баз данных SharePoint Server 2016. Вы увидите сведения для каждой базы данных: <br/><br/> - Размер <br/> - Рекомендации по масштабированию <br/> - Особенности ввода-вывода <br/> - Требования <br/><br/>  На первой странице показаны SharePoint системные базы данных и приложения-службы с несколькими базами данных. На второй странице представлены сведения о приложениях служб с одной базой данных. <br/><br/>  Дополнительные сведения см. в описании типов и описаний [базы данных в SharePoint Server 2016.](/SharePoint/technical-reference/database-types-and-descriptions)|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Архитектурные модели Microsoft Skype для бизнеса 2015

|Item|Описание|
|---|---|
|[![Эскиз для плаката Skype для бизнеса архитектурных моделей.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=55022)|На этом плакате описывается Skype для бизнеса Online, локальной, гибридной и облачной частной ветви exchange (PBX). В нем также описывается интеграция Exchange и SharePoint конфигураций, о которые должны знать разработчики бизнес-решений и архитекторы решений. <br/><br/> Плакат предназначен для ИТ-специалистов для повышения осведомленности о фундаментальных архитектурных моделях, с помощью которых Skype для бизнеса и Skype для бизнеса локального использования. <br/><br/>Начните с конфигурации, которая наилучшим образом соответствует потребностям и планам организации. При необходимости рассмотрите и используйте другие конфигурации. Например, можно рассмотреть интеграцию с Exchange и SharePoint решением, которое будет использовать предложение облачной PBX Microsoft.|
   
## <a name="platform-options-posters"></a>Афиши с вариантами платформ

ИТ-плакаты SharePoint 2013, Exchange 2013 и Lync 2013 предоставляют возможность сравнить методы развертывания с первого взгляда. На каждом плакате перечислены все конфигурации или параметры платформы. В нем содержится следующая информация для каждого параметра:
  
- **Обзор.** Краткое описание платформы, включая концептуальную схему.
    
- **Наиболее подходящие** для: распространенные сценарии, идеально подходящие для платформы.
    
- **Требования к лицензиям.** Лицензии, необходимые для развертывания.
    
- **Задачи архитектуры.** Решения, которые необходимо принять в качестве архитектора.
    
- **Задачи и обязанности** ИТ-специалистов. Ежедневные обязанности, которые необходимо планировать ИТ-сотрудникам.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Варианты платформы SharePoint 2013

|Item|Описание|
|---|---|
|[![Эскиз изображения плаката SharePoint платформы 2013 г.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=40332)|Для лиц, принимающих решения и архитекторов, на этом плакате показаны параметры платформы для SharePoint 2013 г., SharePoint в Microsoft 365, локального гибрида с развертыванием Microsoft 365, Azure и локального развертывания. Он включает обзор каждой архитектуры, рекомендаций, требований к лицензиям и списков задач архитектора и ИТ-профессионала для каждой платформы. На плакате выделено несколько SharePoint решений в Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Варианты платформы Exchange 2013

|Item|Описание|
|---|---|
|[![Эскиз изображения плаката Exchange платформы.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=42676)|Для лиц, принимающих решения и архитекторов, на этом плакате описываются параметры платформы для Exchange 2013 г. Клиенты могут выбирать Exchange Online с Microsoft 365, гибридными Exchange, Exchange Server локальной и Exchange. На плакате подробно по каждому архитектурному варианту, включая идеальные сценарии для каждого, требования к лицензии и обязанности ИТ-профессионалов.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Варианты платформы Lync 2013

|Item|Описание|
|---|---|
|[![Эскиз изображения плаката Lync 2013 Platform Options.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41677)|Для лиц, принимающих решения и архитекторов, на этом плакате описываются параметры платформы для Lync 2013. Клиенты могут выбирать из Lync Online с Microsoft 365, гибридной Lync, Lync Server локальной и принимающей Lync. В плакате ИТ-функции подробно извесятся о каждом архитектурном варианте, включая идеальные сценарии для каждого из них, требования к лицензии и обязанности ИТ-профессионалов.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Афиши с решениями SharePoint в Azure

На ИТ-плакатах SharePoint Azure покажут решения на основе Azure, SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Сайты Интернета в Microsoft Azure с SharePoint Server 2013

|Item|Описание|
|---|---|
|[![Изображение веб-сайтов в Azure с помощью плаката SharePoint Server 2013.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41992)|На этом плакате описаны основные действия по проектированию и рекомендованная архитектура для сайтов, стоящих перед Интернетом в Azure.  <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Сайты Интернета в Azure с SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Архитектуры Azure для SharePoint 2013 г.](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Интернет-сайты в Azure SharePoint 2013 г.

|Item|Описание|
|---|---|
|[![Изображение веб-сайтов в Microsoft Azure для SharePoint Server 2013.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41991)|Используйте этот пример дизайна в качестве отправной точки для собственной архитектуры веб-сайта в Azure с SharePoint Server 2013. <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Сайты Интернета в Azure с SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Архитектуры Azure для SharePoint 2013 г.](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Аварийное восстановление SharePoint в Microsoft Azure

|Item|Описание|
|---|---|
|[![Изображение плаката для процесса SharePoint аварийного восстановления в Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41993)|На этой афише для ИТ-специалистов отображены принципы создания архитектуры для среды аварийного восстановления в Azure. <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [SharePoint Восстановление аварийного восстановления сервера 2013 в Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Архитектуры Azure для SharePoint 2013 г.](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>См. также

- [Центр архитектуры и решений Microsoft 365](../solutions/index.yml)
  
- [Модели облачной архитектуры Майкрософт](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 руководства лаборатории тестирования](m365-enterprise-test-lab-guides.md)
  
- [Гибридные решения](hybrid-solutions.md)