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
description: Сводка. Здесь вы найдете афиши для ИТ-специалистов с описанием архитектурных моделей, развертывания и платформ для SharePoint, Exchange, Skype для бизнеса и Lync.
ms.openlocfilehash: 67f1018c70dfc86306b0d1e7ceb6061a166b3db8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693361"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Архитектурные модели для SharePoint, Exchange, Skype для бизнеса и Lync

На этих афишах для ИТ-специалистов описаны модели архитектуры и варианты развертывания SharePoint, Exchange, Skype для бизнеса и Lync. Эти ресурсы содержат также сведения о конфигурации для развертывания SharePoint в Microsoft Azure.
  
С помощью Microsoft 365 вы можете предоставлять пользователям знакомые функции совместной работы и коммуникации в составе облачной службы.  За некоторыми исключениями, пользовательские интерфейсы в локальной среде и Microsoft 365 одинаковы. Этот единый подход несколько затрудняет выбор среды для рабочих нагрузок и поднимает следующие вопросы:
  
- Как определить, какой вариант платформы использовать для отдельных рабочих нагрузок?
    
- Имеет ли смысл оставлять какую-либо службу локальной?
    
- В каком случае целесообразно использовать гибридное развертывание?
    
- Какова роль Microsoft Azure?
    
- Какие конфигурации поддерживаются для рабочих нагрузок Office Server в Azure?
    
> [!TIP]
> Большинство плакатов на этой странице доступны на нескольких языках, включая английский, испанский, итальянский, китайский, корейский, немецкий, португальский, русский, французский и японский. Чтобы скачать плакат на одном из этих языков, нажмите ссылку **Другие языки**.
  
Ждем ваших отзывов по адресу [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
На этой странице есть ссылки на следующие афиши:
  
- **Афиши с архитектурными моделями.**  Эти ресурсы помогут определить идеальную платформу и конфигурацию для SharePoint 2016 и Skype для бизнеса 2015.
    
  - [Архитектурные модели Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Базы данных SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Архитектурные модели Microsoft Skype для бизнеса 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Афиши с вариантами платформ.**  Эти ресурсы помогут определить идеальную платформу и конфигурацию для SharePoint 2013, Exchange 2013 и Lync 2013.
    
  - [Варианты платформы SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Варианты платформы Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Варианты платформы Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Афиши с решениями SharePoint Server 2013 в Azure.**  Эти афиши для ИТ-специалистов помогут определить конфигурацию для рабочих нагрузок SharePoint Server 2013 в службах инфраструктуры Azure.
    
  - [Веб-сайты в Microsoft Azure, использующие SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Пример проекта: веб-сайты в Microsoft Azure для SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Аварийное восстановление SharePoint в Microsoft Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Афиши с архитектурными моделями

Эти новые афиши для ИТ-специалистов, посвященные SharePoint 2016 и Skype для бизнеса 2015, позволяют сравнивать различные методы развертывания и созданы в удобном для печати формате. На каждой афише перечислены все доступные варианты конфигураций или платформ, а также указаны следующие сведения о каждом варианте:
  
- **Общие сведения**. Кратное описание платформы, включая концептуальную схему.
    
- **Оптимально для**. Распространенные сценарии, идеально подходящие для определенной платформы.
    
- **Требования к лицензированию**. Лицензии, необходимые для развертывания.
    
- **Задачи архитектуры**. Решения, которые вам нужно принять как архитектору.
    
- **Задачи или обязанности ИТ-специалистов**. Ежедневные обязанности, которые нужно запланировать ИТ-специалистам.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-2016-architectural-models"></a>Архитектурные модели Microsoft SharePoint 2016

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Эскиз афиши архитектурных моделей SharePoint 2016](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=52650) <br/> | На этой афише для ИТ-специалистов описаны конфигурации SharePoint Online, Microsoft Azure и локальной среды SharePoint, которые необходимо знать лицам, принимающим бизнес-решения, и архитекторам решений. <br/><br/> - **SharePoint Online (SaaS)**. Используйте SharePoint по подписке в рамках модели SaaS. <br/> - **Гибридная конфигурация SharePoint**. Перемещайте сайты и приложения SharePoint в облако тогда, когда вам удобно. <br/> - **SharePoint в Azure (IaaS)**. Перенесите свою локальную среду в Microsoft Azure и разверните там серверы SharePoint 2016. (Это рекомендуется для сред с высоким уровнем доступности, сред аварийного восстановления, а также сред разработки и тестирования.) <br/> - **Локальная среда SharePoint**. Планируйте, развертывайте, обслуживайте и настраивайте среду SharePoint в своем центре обработки данных. <br/> |
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Базы данных SharePoint Server 2016

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Эскиз плаката о базах данных SharePoint Server 2016](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)          ](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=55041) <br/> | На этом плакате для IT-специалистов представлен краткий справочник по базам данных SharePoint Server 2016. По каждой базе данных указано следующее: <br/><br/> - Размер <br/> - Рекомендации по масштабированию <br/> - Особенности ввода-вывода <br/> - Требования <br/><br/>  На первой странице приведены сведения о системных базах данных SharePoint и приложениях служб с несколькими базами данных. На второй странице представлены сведения о приложениях служб с одной базой данных. <br/><br/>  Дополнительные сведения о базах данных SharePoint Server 2016 см. в статье [Типы и описания баз данных в SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions) <br/> |
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Архитектурные модели Microsoft Skype для бизнеса 2015

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Эскиз плаката архитектурных моделей Skype для бизнеса](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)          ](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=55022) <br/> |На этом плакате описаны конфигурации со Skype для бизнеса Online, локальные и гибридные конфигурации, конфигурации с облачной УАТС, а также с интеграцией Exchange и SharePoint, о которых необходимо знать архитекторам решений и лицам, принимающим бизнес-решения. <br/><br/> Эта серия плакатов предназначена для ИТ-специалистов, чтобы они могли больше разбираться в различных базовых архитектурных моделях, благодаря которым можно использовать Skype для бизнеса Online и Skype для бизнеса в локальной среде. <br/><br/>Начните с конфигурации, которая больше всего соответствует потребностям организации и будущим планам. При необходимости используйте другие конфигурации. Например, может понадобиться интеграция Exchange и SharePoint или решение, использующее облачную УАТС корпорации Майкрософт.  <br/> |
   
## <a name="platform-options-posters"></a>Афиши с вариантами платформ

Эти афиши для ИТ-специалистов, посвященные SharePoint 2013, Exchange 2013 и Lync 2013, позволяют сравнивать различные методы развертывания и созданы в большом формате для удобства понимания. На каждой афише перечислены все доступные варианты конфигураций или платформ, а также указаны следующие сведения о каждом варианте:
  
- **Общие сведения**. Кратное описание платформы, включая концептуальную схему.
    
- **Оптимально для**. Распространенные сценарии, идеально подходящие для определенной платформы.
    
- **Требования к лицензированию**. Лицензии, необходимые для развертывания.
    
- **Задачи архитектуры**. Решения, которые вам нужно принять как архитектору.
    
- **Задачи или обязанности ИТ-специалистов**. Ежедневные обязанности, которые нужно запланировать ИТ-специалистам.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Варианты платформы SharePoint 2013

****

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Эскиз вариантов платформы SharePoint 2013](../media/SP-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=40332) <br/> |Эта модель, предназначенная для лиц, принимающих бизнес-решения, и архитекторов, описывает варианты платформ для SharePoint 2013, SharePoint в Microsoft 365, локального гибридного развертывания в Microsoft 365, Azure, а также локального развертывания.  Она содержит обзор каждой архитектуры, рекомендации, лицензионные требования, а также списки задач для архитекторов и ИТ-специалистов по каждой платформе. Также рассмотрено несколько решений SharePoint в Azure.  <br/> |
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Варианты платформы Exchange 2013

****

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Эскиз вариантов платформы Exchange](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=42676) <br/> |В этой модели описаны доступные платформы для Exchange 2013 для лиц, принимающих бизнес-решения, и архитекторов. Клиенты могут выбрать Exchange Online с Microsoft 365, гибридную среду Exchange, локальную среду Exchange Server и размещенный Exchange. Плакат содержит сведения о каждом варианте архитектуры, включая оптимальные сценарии, требования к лицензиям и описание обязанностей ИТ-специалистов. <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Варианты платформы Lync 2013

****

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Эскиз вариантов платформы Lync](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41677) <br/> |В этой модели описаны доступные платформы для Lync 2013 для лиц, принимающих бизнес-решения, и архитекторов. Клиенты могут выбрать Lync Online с Microsoft 365, гибридную среду Lync, локальный сервер Lync Server и размещенное решение Lync. Афиша для ИТ-специалистов содержит сведения о каждом варианте архитектуры, включая оптимальные сценарии, требования к лицензиям и описание обязанностей ИТ-специалистов.  <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Афиши с решениями SharePoint в Azure

На этих афишах для ИТ-специалистов в большом формате показаны решения, предусматривающие использование SharePoint Server 2013 и Azure.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Веб-сайты в Microsoft Azure с использованием SharePoint Server 2013

****

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Изображение веб-сайтов в Azure, использующих SharePoint](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41992) <br/> |На этой афише представлены описания рекомендуемых вариантов архитектуры доступных в Интернете сайтов в Azure.  <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Веб-сайты в Microsoft Azure, использующие SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Архитектуры Microsoft Azure для SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="DesignSampleInternetSites"> </a>
### <a name="design-sample-internet-sites-in-microsoft-azure-for-sharepoint-2013"></a>Пример проекта: веб-сайты в Microsoft Azure для SharePoint 2013

****

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Изображение примера проекта: веб-сайты в Microsoft Azure для SharePoint 2013](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41991) <br/> |Используйте этот пример проектирования в качестве начальной точки при создании собственной архитектуры для доступного в Интернете сайта в Azure с использованием SharePoint Server 2013. <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Веб-сайты в Microsoft Azure, использующие SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Архитектуры Microsoft Azure для SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Аварийное восстановление SharePoint в Microsoft Azure

****

|**Элемент**|**Описание**|
|:-----|:-----|
|[![Процесс аварийного восстановления SharePoint в Azure](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Другие языки](https://www.microsoft.com/download/details.aspx?id=41993) <br/> |На этой афише для ИТ-специалистов отображены принципы создания архитектуры для среды аварийного восстановления в Azure. <br/><br/> Дополнительные сведения см. в следующих статьях:  <br/><br/> - [Аварийное восстановление SharePoint Server 2013 в Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Архитектуры Microsoft Azure для SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
## <a name="see-also"></a>См. также

[Центр архитектуры и решений Microsoft 365](../solutions/solution-architecture-center.md)
  
[Иллюстрации по Microsoft Cloud для корпоративных архитекторов](../solutions/cloud-architecture-models.md)
  
[Руководства по лаборатории тестирования Microsoft 365](m365-enterprise-test-lab-guides.md)
  
[Гибридные решения](hybrid-solutions.md)

