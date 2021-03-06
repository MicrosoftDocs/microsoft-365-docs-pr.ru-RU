---
title: Модель данных аналитики использования Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: 'Узнайте, как аналитика использования подключается к API и предоставляет ежемесячную тенденцию использования различных Microsoft 365 служб.  '
ms.openlocfilehash: 877ad005e3ff7f7537247963fafcab5fb1ff6c74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580754"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Модель данных аналитики использования Microsoft 365

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Данные для таблиц Microsoft 365 использования

Microsoft 365 аналитика использования подключается к API, который предоставляет многомерную модель данных. API, Microsoft 365 для создания данных, используются из различных, общедоступных, Graph API. Функция API Microsoft 365 аналитики использования сама по себе недоступна.
  
> [!NOTE]
> Дополнительные сведения см. в Microsoft 365 отчеты об использовании в [Microsoft Graph.](/graph/api/resources/report) 
  
Этот API предоставляет сведения о ежемесячной тенденции использования различных Microsoft 365 служб. Точные данные, возвращаемые API, описаны в таблице ниже.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Таблицы данных, возвращенные API Microsoft 365 отчетов

|**Имя таблицы**|**Сведения в таблице**|**Диапазон дат**|
|:-----|:-----|:-----|
|Tenant Product Usage  <br/> |Содержит ежемесячные итоги включенных, активных пользователей, сохраненных пользователей, впервые и совокупных активных пользователей.  <br/> |Содержит ежемесячные агрегированные данные за 12-месячный скользящий период, который включает текущий неполный месяц.  <br/> |
|Tenant Product Activity  <br/> |Содержит ежемесячные итоги действий и количество активных пользователей для различных действий в продуктах.  <br/> Сведения о действиях в продуктах, включаемых в эту таблицу данных, см. в [определении активного пользователя](active-user-in-usage-reports.md).      <br/> |Содержит ежемесячные агрегированные данные за 12-месячный скользящий период, который включает текущий неполный месяц.  <br/> |
|Tenant Office Licenses  <br/> |Содержит данные о количестве подписок на Microsoft Office, назначенных пользователям.  <br/> |Содержит данные состояния за конец месяца за 12-месячный период, включая текущий неполный месяц.  <br/> |
|Tenant Mailbox Usage  <br/> |Содержит данные о почтовом ящике пользователя, об общем учете почтовых ящиков и о том, как используется хранилище.  <br/> |Содержит данные состояния за конец месяца за 12-месячный период, включая текущий неполный месяц.  <br/> |
|Tenant Client Usage  <br/> |Содержит данные о количестве пользователей, которые активно используют определенные клиенты и устройства для подключения к Exchange Online, Skype для бизнеса и Yammer.  <br/> |Содержит ежемесячные агрегированные данные за 12-месячный скользящий период, который включает текущий неполный месяц.  <br/> |
|Tenant SharePoint Online Usage  <br/> |Содержит данные о сайтах SharePoint, включая сайты групп и рабочих групп, в том числе общее количество сайтов, количество документов на сайте, количество файлов по типу активности и используемый объем хранилища.  <br/> |Содержит данные состояния за конец месяца за 12-месячный период, включая текущий неполный месяц.  <br/> |
|Tenant OneDrive for Business Usage  <br/> |Содержит данные об учетных записях OneDrive, включая их количество, число документов в папках OneDrive, используемый объем хранилища и количество файлов по типу активности.  <br/> |Содержит данные состояния за конец месяца за 12-месячный период, включая текущий неполный месяц.  <br/> |
|Использование Microsoft 365 групп клиента  <br/> |Содержит данные об использовании Microsoft 365 групп, включая почтовые ящики, SharePoint и Yammer.  <br/> |Содержит данные состояния за конец месяца за 12-месячный период, включая текущий неполный месяц.  <br/> |
|Tenant Office Activation  <br/> |Содержит данные о количестве активаций Office, количестве активации на устройство (Android/iOS/Mac/PC), активациях по плану службы, например, Приложения Microsoft 365 для предприятий, Visio, Project.  <br/> |Содержит данные состояния за конец месяца за 12-месячный период, включая текущий неполный месяц.  <br/> |
|User State  <br/> |Содержит метаданные о пользователях, включая отображаемое имя пользователя, назначенные продукты, расположение, отдел, должность и организацию. Эти данные о пользователях, которым была назначена лицензия в течение последнего месяца. Каждый пользователь уникально представлен пользовательским ИД.  <br/> |Это данные о пользователях, которым были назначены лицензии в течение последнего полного месяца.  <br/> |
|User Activity  <br/> |Содержит сведения о действиях, выполняемых лицензированными пользователями, на уровне каждого пользователя.  <br/> Сведения о действиях в продуктах, включаемых в эту таблицу данных, см. в [определении активного пользователя](active-user-in-usage-reports.md).      <br/> |Это данные о пользователях, которые выполняли действия в любой из служб в течение последнего полного месяца.  <br/> |
   
Разверните следующие разделы, чтобы ознакомиться с подробными сведениями о каждой таблице данных.
  
### <a name="data-table---user-state"></a>Таблица данных User State

Эта таблица содержит сведения об уровне пользователя для всех пользователей, которые имеют лицензию, назначенную им в течение последнего полного месяца. Данные берутся из Azure Active Directory.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|UserId  <br/> |Уникальный пользовательский ID, который представляет пользователя и позволяет присоединяться к другим таблицам данных в наборе данных.  <br/> |
|Timeframe  <br/> |Значение месяца, для которого предлагаются данные.  <br/> |
|UPN  <br/> |Имя участника-пользователя, однозначно определяющее пользователя для соединения с внешними источниками данных.  <br/> |
|DisplayName  <br/> |Отображаемое имя пользователя.  <br/> |
|IDType  <br/> |Тип ID установлен до 1, если пользователь является пользователем Yammer, который подключается с помощью Yammer ID или 0, если он подключается к Yammer с помощью Microsoft 365 ID.  <br/> Значение 1 означает, что этот пользователь подключается к Yammer с Yammer, а не с Microsoft 365 ID  <br/> |
|HasLicenseEXO  <br/> |Задайте значение true, если пользователю назначена лицензия и разрешено использовать Exchange.  <br/> |
|HasLicenseODB  <br/> |Задайте значение true, если пользователю назначена лицензия и разрешено использовать OneDrive для бизнеса.  <br/> |
|HasLicenseSPO  <br/> |Задайте значение true, если пользователю назначена лицензия и разрешено использовать SharePoint Online.  <br/> |
|HasLicenseYAM  <br/> |Задайте значение true, если пользователю назначена лицензия и разрешено использовать Yammer.  <br/> |
|HasLicenseSFB  <br/> |Задайте значение true, если пользователю назначена лицензия и разрешено использовать Skype для бизнеса.  <br/> |
|HasLicenseTeams  <br/> |Установите для true, если пользователю назначена лицензия и вы можете использовать Microsoft Teams.  <br/> |
|Company  <br/> |Данные о компании, указанные в Azure Active Directory для этого пользователя.  <br/> |
|Department  <br/> |Данные об отделе, указанные в Azure Active Directory для этого пользователя.  <br/> |
|LocationCity  <br/> |Данные о городе, указанные в Azure Active Directory для этого пользователя.  <br/> |
|LocationCountry  <br/> |Данные о стране, указанные в Azure Active Directory для этого пользователя.  <br/> |
|LocationState  <br/> |Данные об области, республике, крае или округе, указанные в Azure Active Directory для этого пользователя.  <br/> |
|LocationOffice  <br/> |Офис пользователя.  <br/> |
|Title  <br/> |Данные о должности, указанные в Azure Active Directory для этого пользователя.  <br/> |
|Deleted  <br/> |True, если пользователь был удален из Microsoft 365 за последний полный месяц.  <br/> |
|DeletedDate  <br/> |Дата удаления пользователя из Microsoft 365.  <br/> |
|YAM_State  <br/> |Состояния пользователя в Yammer могут быть активными, удаленными или приостановленными.  <br/> |
|YAM_ActivationDate  <br/> |Дата перехода пользователя в состояние "Активен" в Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Дата перехода пользователя в состояние "Удален" в Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Дата перехода пользователя в состояние "Приостановлен" в Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Таблица данных User Activity

Эта таблица содержит данные о каждом пользователе, который выполнял действия в любой из служб в предыдущем месяце.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|UserID  <br/> |Уникальный пользовательский ID, который представляет пользователя и позволяет присоединяться к другим таблицам данных в наборе данных.  <br/> |
|IDType  <br/> |Тип ID установлен до 1, если пользователь является пользователем Yammer, который подключается с помощью Yammer ID или 0, если он подключается к Yammer с помощью Microsoft 365 ID.  <br/> Значение 1 означает, что этот пользователь подключается к Yammer с Yammer, а не с Microsoft 365 ID  <br/> |
|Timeframe  <br/> |Значение месяца, для которого предлагаются данные.  <br/> |
|EXO_EmailSent  <br/> |Количество отправленных сообщений электронной почты.  <br/> |
|EXO_EmailReceived  <br/> |Количество полученных сообщений электронной почты.  <br/> |
|EXO_EmailRead  <br/> |Количество выполняемой пользователем активности чтения электронной почты, это может быть несколько раз чтение уже прочитаного сообщения электронной почты или полученного ранее сообщения электронной почты.  <br/> |
|EXO_AppointmentCreated  <br/> |Количество созданных встреч.  <br/> |
|EXO_MeetingAccepted  <br/> |Количество принятых собраний.  <br/> |
|EXO_MeetingCancelled  <br/> |Количество отмененных собраний.  <br/> |
|EXO_MeetingDeclined  <br/> |Количество собраний сократилось.  <br/> |
|EXO_MeetingSent  <br/> |Количество отправленных собраний.  <br/> |
|ODB_FileViewedModified  <br/> |Количество файлов, с которыми этот пользователь работал (например, создавал, обновлял, удалял, просматривал или скачивал их), в любом хранилище OneDrive для бизнеса.  <br/> |
|ODB_FileSynched  <br/> |Количество файлов, которые этот пользователь синхронизировал, в любом хранилище OneDrive для бизнеса.  <br/> |
|ODB_FileSharedInternally  <br/> |Количество файлов, которые этот пользователь делил внутренне из OneDrive для бизнеса или пользователей в группах (в том числе внешних пользователей).  <br/> |
|ODB_FileSharedExternally  <br/> |Количество файлов, к которым этот пользователь предоставил внешний доступ, в любом хранилище OneDrive для бизнеса.  <br/> |
|ODB_AccessByOwner  <br/> |Количество файлов, с которыми работал пользователь, в его собственном хранилище OneDrive для бизнеса.  <br/> |
|ODB_AccessOthers  <br/> |Количество файлов, с которыми работал пользователь, в хранилище OneDrive для бизнеса, принадлежащем другому пользователю.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Количество файлов, с которыми работал этот пользователь, на любом сайте группы.  <br/> |
|SPO_GroupFileSynched  <br/> |Количество файлов, которые этот пользователь синхронизировал, на любом сайте группы.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Количество файлов, которые были общими для пользователей в организации или пользователей в группах (в том числе внешних пользователей).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Количество файлов, к которым этот пользователь предоставил внешний доступ, на любом сайте группы.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Количество файлов, с которыми работал пользователь, на его собственном сайте группы.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Количество файлов, с которыми работал пользователь, на сайте группы, принадлежащем другому пользователю.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Количество файлов, с которыми этот пользователь взаимодействовал на любом другом сайте.  <br/> |
|SPO_OtherFileSynched  <br/> |Количество файлов, синхронизированных этим пользователем с любого другого сайта.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Количество файлов, которые этот пользователь делил внутренне с любого другого сайта или с пользователями в группах (в том числе внешних пользователей). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Количество файлов, которые этот пользователь поделился внешне с любого другого сайта.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Количество сайтов, с которые пользователь взаимодействовал, находится на другом сайте, который им принадлежит.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Количество сайтов, с которые пользователь взаимодействовал, находится на другом сайте, который принадлежит другому пользователю.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Количество файлов, с которыми работал этот пользователь, на любом сайте рабочей группы.  <br/> |
|SPO_TeamFileSynched  <br/> |Количество файлов, которые этот пользователь синхронизировал, на любом сайте рабочей группы.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Количество файлов, которые этот пользователь делил внутренне с любого сайта группы или с пользователями в группах (в том числе внешних пользователей).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Количество файлов, к которым этот пользователь предоставил внешний доступ, на любом сайте рабочей группы.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Количество файлов, с которыми работал пользователь, на принадлежащем ему сайте рабочей группы.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Количество файлов, с которыми работал пользователь, на сайте рабочей группы, принадлежащем другому пользователю.  <br/> |
|Teams_ChatMessages  <br/> |Количество отправленных сообщений чата.  <br/> |
|Teams_ChannelMessage  <br/> |Количество сообщений, которые были размещены в каналах.  <br/> |
|Teams_CallParticipate  <br/> |Количество вызовов, в которые принимал участие пользователь.  <br/> |
|Teams_MeetingParticipate  <br/> |Количество собраний, к которые присоединился пользователь.  <br/> |
|Teams_HasOtherAction  <br/> |Значение Boolean, если пользователь выполнял другие действия в Microsoft Teams.  <br/> |
|YAM_MessagePost  <br/> |Количество Yammer сообщений, которые этот пользователь опубликовал.  <br/> |
|YAM_MessageLiked  <br/> |Количество Yammer сообщений, которые понравились этому пользователю.  <br/> |
|YAM_MessageRead  <br/> |Количество сообщений Yammer, которые читает этот пользователь.  <br/> |
|SFB_P2PSummary  <br/> |Количество одноранговых сеансов, в которых участвовал этот пользователь.  <br/> |
|SFB_ConfOrgSummary  <br/> |Количество сеансов конференц-связи, организованных пользователем.  <br/> |
|SFB_ConfPartSummary  <br/> |Количество сеансов конференц-связи, в которых участвовал пользователь.  <br/> |

> [!NOTE]
> Teams_HasOtherAction означает, что пользователь считается активным, но имеет нулевое значение для сообщений чата, звонков 1:1, сообщений каналов, общего собрания и собраний, организованных.
   
### <a name="data-table---tenant-product-usage"></a>Таблица данных Tenant Product Usage

Эта таблица содержит данные об усыновлении за месяц с точки зрения включить, активную, возвращаемую и впервые пользовательную информацию для каждого продукта в Microsoft 365. Значения Microsoft 365 представляют активное использование в любом из продуктов.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|Product  <br/> |Название продукта, сведения об использовании которого собираются. Microsoft 365 в столбце продукта представляет активность в любом из продуктов  <br/> |
|Timeframe  <br/> |Значение месяца. В таблице содержится одна строка для каждого продукта и каждого из последних 12 месяцев, включая текущий неполный месяц.  <br/> |
|EnabledUsers  <br/> |Количество пользователей, включенных для использования продукта для значения времени, если пользователь был включен в течение части месяца, они по-прежнему считаются.  <br/> |
|ActiveUsers  <br/> |Число пользователей, которые выполняли преднамеренные действия в продукте для значения времени.  <br/> Пользователь продукта считается активным в определенном месяце, если он выполнил одно из основных действий в продукте. Основные действия указаны в таблице **Tenant Product Activity**.  <br/> |
|CumulativeActiveUsers  <br/> |Количество пользователей, которые имеют доступ к продукту и использовали его хотя бы один раз с начала сбора данных в новой системе учета использования до указанного месяца.  <br/> |
|MoMReturningUsers  <br/> |Количество пользователей, которые были активны в указанный месяц и месяц, предшествовавший ему.  <br/> |
|FirstTimeUsers  <br/> |Количество пользователей, которые впервые выполнили действия в указанный месяц с начала сбора данных в новой системе учета использования.  <br/> Пользователь считается новым в определенном месяце, если его активность выявлена впервые с начала сбора данных в этой новой системе отчетности. После подсчета в качестве первого пользователя, даже если этот пользователь имеет большой пробел в своей деятельности, он никогда не будет считаться снова в качестве первого пользователя  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Таблица данных Tenant Product Activity

В этой таблице ежемесячная сумма действий и количество активных пользователей для различных действий в продуктах.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|Timeframe  <br/> |Значение месяца. В таблице содержится одна строка для каждого продукта и каждого из последних 12 месяцев, включая текущий неполный месяц.  <br/> |
|Product  <br/> |Имя продукта в Microsoft 365, для которого доступны данные об использовании.  <br/> |
|Activity  <br/> |Название действия в продукте, которое представляет активное использование продукта.  <br/> |
|ActivityCount  <br/> |Общее количество действий для каждого типа активности, выполненных в продукте всеми пользователями.  <br/> **Примечание.** Для SharePoint Online и OneDrive для бизнеса это значение показывает количество отдельных документов, с которыми работали пользователи.      <br/> |
|ActiveUserCount  <br/> |Количество пользователей, которые выполняли действия в продукте.  <br/> |
|TotalDurationInMinute  <br/> |Количество минут для всех активных пользователей, которые использовали голосовую или видеосвязь в Skype для бизнеса.  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Таблица данных Tenant Mailbox Usage

Эта таблица состоит из сводных данных для всех лицензированных Exchange Online пользователей, у которых есть почтовый ящик пользователя. Это сведения обо всех почтовых ящиках пользователей по состоянию на конец месяца. В этой таблице данные за отдельные месяцы не суммируются. Данные за последний месяц отражают наиболее актуальное состояние.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|TotalMailboxes  <br/> |Количество почтовых ящиков пользователей для Microsoft 365 подписки.  <br/> |
|IssueWarningQuota  <br/> |Общая квота на выдачу предупреждений в почтовых ящиках всех пользователей.  <br/> |
|ProhibitSendQuota  <br/> |Общая квота для запрета отправки по всем почтовым ящикам пользователей.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Общая квота для запрета отправки и получения по всем почтовым ящикам пользователей.  <br/> |
|TotalItemBytes  <br/> |Объем хранилища, занимаемый всеми почтовыми ящиками пользователей (в байтах).  <br/> |
|Почтовые ящикиNoWarning  <br/> |Количество почтовых ящиков пользователей, которые не превысили порог предупреждения об объеме хранилища.  <br/> |
|MailboxesIssueWarning  <br/> |Количество почтовых ящиков пользователей, для которых было выдано предупреждение о квоте хранилища.  <br/> |
|Почтовые ящикиExceedSendQuota  <br/> |Количество почтовых ящиков пользователей, для которых превышена квота отправки.  <br/> |
|Почтовые ящикиExceedSendReceiveQuota  <br/> |Количество почтовых ящиков пользователей с превышением квоты отправки и получения.  <br/> |
|Удаленные почтовые ящики  <br/> |Количество почтовых ящиков пользователей, удаленных в указанный период времени.  <br/> |
|Timeframe  <br/> |Значение месяца.  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Таблица данных Tenant Client Usage

В этой таблице помесячные сводные данные о клиентах, которые пользователи используют для подключения к Exchange Online, Skype для бизнеса и Yammer. Таблица пока не содержит аналогичных данных для SharePoint Online и OneDrive для бизнеса.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|Product  <br/> |Имя продукта в Microsoft 365, для которого доступны данные об использовании клиента.  <br/> |
|ClientId  <br/> |Имя каждого устройства, используемого для подключения к продукту.  <br/> |
|UserCount  <br/> |Количество пользователей, которые применяли каждый из клиентов каждого продукта.  <br/> |
|Timeframe  <br/> |Значение месяца.  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Таблица данных Tenant SharePoint Online Usage

Эта таблица состоит из ежемесячных сводных данных об использовании или активности веб-сайтов SharePoint Online. Это касается только сайтов групп и групп. В этом столбце представлено состояние SharePoint Online, например, если пользователь создал пять документов и использовал 10 МБ для общего хранилища, а затем удалил некоторые файлы, а затем добавил несколько файлов, чтобы в конце месяца состояние файлов было семь, в результате чего используется пять МБ хранилища, значение, представленное в этой таблице, заканчивается состоянием месяца. Эта таблица скрыта, чтобы избежать дублирования подсчета агрегаций, и используется в качестве источника для создания двух эталонных таблиц.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|SiteType  <br/> |Значение типа сайта: any/team/group (любой сайт, сайт рабочей группы или сайт группы). Значение any представляет сайты обоих типов.  <br/> |
|TotalSites  <br/> |Количество сайтов, существовавших на конец периода.  <br/> |
|DocumentCount  <br/> |Общее количество документов, существовавших на сайте на конец периода.  <br/> |
|Diplansed  <br/> |Общий использованный объем хранилища (суммарно на всех сайтах) на конец периода.  <br/> |
|ActivityType  <br/> |Количество сайтов, на которых зарегистрированы различные типы действий с файлами: any/active files/files shared EXT/INT/files synched (любое, активные файлы, предоставление внешнего или внутреннего общего доступа, синхронизация файлов).  <br/> Представляет любое действие файла, которое было выполнено.  <br/> |
|SitesWithOwnerActivities  <br/> |Количество активных сайтов, на которых владелец выполнил определенное действие с файлом. Вы можете получить владельца сайта из командной команды PowerShell **get-sposite.** Это лицо, ответственное за сайт.   <br/> |
|SitesWithNonOwnerActivities  <br/> |Суммарное количество активных сайтов за месяц, на которых пользователи, не являющиеся владельцами, выполнили определенные действия с файлами. Вы можете получить владельца сайта из командной команды PowerShell **get-sposite.** Это лицо, ответственное за сайт. <br/> |
|ActivityTotalSites  <br/> |Количество сайтов, на которых в течение периода зарегистрирована любая активность. Здесь учитываются и те сайты с зарегистрированной активностью, которые на конец периода уже были удалены.  <br/> |
|Timeframe  <br/> |Этот столбец содержит значение даты. Используется в качестве связи "многие к одному" с таблицей Calendar.  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Таблица данных — использование OneDrive клиента

Эта таблица содержит сведения об учетных записях OneDrive, такие как число учетных записей, количество документов в них, используемое хранилище, число файлов по типу действий. Таблица отражает состояние учетных записей OneDrive для бизнеса на конец месяца. Например, если пользователь создал пять документов, которые использовали 10 МБ хранилища, а затем удалил несколько файлов и добавил еще несколько файлов, чтобы в конце месяца у них было семь файлов с использованием 5 МБ хранилища, то в конце месяца значение месяца представлено в этой таблице в конце месяца.
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|SiteType  <br/> |Содержит значение OneDrive.  <br/> |
|TotalSites  <br/> |Количество учетных записей OneDrive для бизнеса, существовавших на конец периода.  <br/> |
|DocumentCount  <br/> |Общее количество документов, существовавших во всех учетных записях OneDrive для бизнеса на конец периода.  <br/> |
|Diplansed  <br/> |Общее хранилище, используемого для OneDrive всех учетных записей в конце таймфрейма.  <br/> |
|ActivityType  <br/> |Количество учетных записей, на которых зарегистрированы различные типы действий с файлами: any/active files/files shared EXT/INT/files synched (любое, активные файлы, предоставление внешнего или внутреннего общего доступа, синхронизация файлов).  <br/> Значение any представляет любые действия с файлами.  <br/> |
|SitesWithOwnerActivities  <br/> |Количество активных учетных записей OneDrive для бизнеса, в которых владелец выполнил определенное действие с файлом.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Количество учетных записей OneDrive для бизнеса, для которых действие с файлом выполнял пользователь, не являющийся владельцем.  <br/> |
|ActivityTotalSites  <br/> |Количество учетных записей OneDrive для бизнеса, в которых было зарегистрировано любое действие в течение периода. Здесь учитываются и те учетные записи OneDrive для бизнеса с зарегистрированной активностью, которые на конец периода уже были удалены.  <br/> |
|Timeframe  <br/> |Этот столбец содержит значение даты. Используется в качестве связи "многие к одному" с таблицей Calendar.  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Таблица данных — использование Microsoft 365 групп клиента

В этой таблице приводится информация об Microsoft 365 групп в организации.
  
****

|**Столбец**|**Описание столбца**|
|:-----|:-----|
|TimeFrame  <br/> |Значение месяца. В таблице содержится одна строка для каждого продукта и каждого из последних 12 месяцев, включая текущий неполный месяц.  <br/> |
|GroupType  <br/> |Тип группы (частный/общедоступный/любой).  <br/> |
|TotalGroups  <br/> |Количество групп в каждом типе группы.  <br/> |
|ActiveGroups  <br/> |Количество активных групп.  <br/> |
|MBX_TotalGroups  <br/> |Количество групп почтовых ящиков.  <br/> |
|MBX_ActiveGroups  <br/> |Количество активных групп почтовых ящиков.  <br/> |
|MBX_TotalActivities  <br/> |Количество действий почтовых ящиков.  <br/> |
|MBX_TotalItems  <br/> |Количество элементов почтового ящика.  <br/> |
|MBX_StorageUsed  <br/> |Количество используемого хранилища почтовых ящиков.  <br/> |
|SPO_TotalGroups  <br/> |Количество SharePoint групп.  <br/> |
|SPO_ActiveGroups  <br/> |Количество активных SharePoint групп.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Количество групп SharePoint, которые имеют доступ к файлам.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Количество групп SharePoint, которые синхронизируются с файлами.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Количество групп SharePoint, которые имеют общие действия внутри организации или с группами (в том числе внешние пользователи).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Количество групп SharePoint, которые имеют общие внешние действия.  <br/> |
|SPO_TotalActivities  <br/> |Количество SharePoint действий.  <br/> |
|SPO_FileAccessedActivities  <br/> |Количество действий SharePoint файлов.  <br/> |
|SPO_FileSyncedActivities  <br/> |Количество синхронизированных действий SharePoint файлов.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Количество общих SharePoint внутренних или групп (в том числе внешних участников).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Количество общих SharePoint внешних действий.  <br/> |
|SPO_TotalFiles  <br/> |Количество SharePoint файлов.  <br/> |
|SPO_ActiveFiles  <br/> |Количество активных SharePoint файлов.  <br/> |
|SPO_StorageUsed  <br/> |Количество используемого SharePoint хранилища.  <br/> |
|YAM_TotalGroups  <br/> |Количество Yammer групп.  <br/> |
|YAM_ActiveGroups  <br/> |Количество активных Yammer групп.  <br/> |
|YAM_LikedActiveGroups  <br/> |Количество групп Yammer, которые имеют похожие действия.  <br/> |
|YAM_PostedActiveGroups  <br/> |Количество групп Yammer, которые имеют почтовые действия.  <br/> |
|YAM_ReadActiveGroups  <br/> |Количество групп Yammer, которые имеют действия чтения.  <br/> |
|YAM_TotalActivities  <br/> |Количество Yammer действий.  <br/> |
|YAM_LikedActivities  <br/> |Количество таких Yammer действий.  <br/> |
|YAM_PostedActivties  <br/> |Количество действий Yammer сообщений.  <br/> |
|YAM_ReadActivites  <br/> |Количество действий Yammer чтения.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Таблица данных Tenant Office Activation

В таблице личные данные о количестве активаций Office в планах служб, например, Приложения Microsoft 365 для предприятий, Visio, Project. Она также включает данные о количестве активаций по типам устройства (Android, iOS, Mac или ПК).
  
|**Имя столбца**|**Описание столбца**|
|:-----|:-----|
|ServicePlanName  <br/> |Список названий планов обслуживания и количество активаций по типу устройств (см. описание столбцов ниже).  <br/> |
|TotalEnabled  <br/> |Количество пользователей, включенных в каждом плане обслуживания, на конец периода.  <br/> |
|TotalActivatedUsers  <br/> |Количество пользователей, активировавших каждый из планов обслуживания, на конец периода.  <br/> |
|AndroidCount  <br/> |Количество активаций на устройствах с Android для каждого плана обслуживания на конец периода.  <br/> |
|iOSCount  <br/> |Количество активаций на устройствах с iOS для каждого плана обслуживания на конец периода.  <br/> |
|MacCount  <br/> |Количество активаций на компьютерах Mac для каждого плана обслуживания на конец периода.  <br/> |
|PcCount  <br/> |Количество активаций на ПК для каждого плана обслуживания на конец периода.  <br/> |
|WinRtCount  <br/> |Количество активаций на устройствах Windows Mobile для каждого плана обслуживания на конец периода.  <br/> |
|Timeframe  <br/> |Этот столбец содержит значение даты. Используется в качестве связи "многие к одному" с таблицей Calendar.  <br/> |
|Content Date  <br/> |Если в столбце Timeframe указан текущий месяц, это значение представляет последнюю дату текущего месяца, на которую доступны данные.  <br/> Если в столбце Timeframe указан предыдущий месяц, это значение представляет его последнюю дату.  <br/> |
