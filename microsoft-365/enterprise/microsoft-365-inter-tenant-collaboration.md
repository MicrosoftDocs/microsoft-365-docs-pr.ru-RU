---
title: Совместная работа между клиентами Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Узнайте, как совместная работа Microsoft 365 работает в разных клиентах и организациях, позволяя различным организациям безопасно работать вместе.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00eacfc21d3223b5b9a1ad420cd5d1d85bf4ea8e
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384831"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Совместная работа между клиентами Microsoft 365

Предположим, что две организации, Fabrikam и Contoso, имеют клиент Microsoft 365 для бизнеса и хотят работать вместе над несколькими проектами; некоторые из них запускаются в течение ограниченного времени, а некоторые — в течение текущего времени. Как Fabrikam и Contoso могут обеспечить более эффективную работу своих людей и групп в разных клиентах Microsoft 365 безопасным образом? Microsoft 365 в сочетании с совместной работой B2B Azure Active Directory (Azure AD) предоставляет несколько вариантов. В этой статье описываются несколько ключевых сценариев, которые могут учитываться fabrikam и Contoso.
  
Варианты совместной работы между клиентами Microsoft 365 включают использование централизованного расположения для файлов и бесед, общий доступ к календарям, обмен мгновенными сообщениями, аудио- и видеозвонки для связи и обеспечение безопасности доступа к ресурсам и приложениям. Используйте следующие таблицы для выбора решений и получения дополнительных данных.
  
## <a name="exchange-online-collaboration-options"></a>Варианты совместной работы Exchange Online

| Цель совместного доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Совместное работы с календарями с другой организацией Microsoft 365 |Администраторы могут настроить различные уровни доступа к календарю в Exchange Online, чтобы разрешить организациям сотрудничать с другими компаниями и позволить пользователям делиться расписаниями (сведениями о доступности) с другими. | <ul><li>[Общий доступ](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) </li><li> [Связи организации](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) </li><li> [Создание связи организации](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) </li><li> [Изменение связи организации ](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) </li><li> [Удаление связи организации](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) </li><li> [Совместное использование календарей с внешними пользователями](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Управление тем, как пользователи делятся календарями с пользователями за пределами организации | Администраторы применяют политики общего доступа к почтовым ящикам пользователей, чтобы контролировать, к кому можно предоставлять общий доступ и каков предоставленный уровень доступа |  <ul><li> [Политики общего доступа](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) </li><li> [Создание политики общего доступа](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) </li><li> [Применение политики общего доступа к почтовым ящикам](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) </li><li> [Изменение, отключение или удаление политики общего доступа](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) </li></ul> |
|Настройка безопасных каналов электронной почты и управление потоком почты с партнерскими организациями | Администраторы создают соединитель для применения безопасности к обмену почтой с партнерской организацией или поставщиком услуг. Соединители принудительно используют шифрование с помощью TLS, а также позволяют применять ограничения на доменные имена или диапазоны IP-адресов, с которых партнеры отправляют электронную почту. |  <ul><li> [Использование протокола TLS службой Exchange Online для защиты электронной почты](https://technet.microsoft.com/library/mt163898.aspx) </li><li> [Настройка потока почты с помощью соединителетов](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) </li><li> [Удаленные домены](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) </li><li> [Настройка соединители для безопасного потока почты с партнерской организацией](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) </li><li> [Практические методики потока почты (обзор)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Варианты совместной работы SharePoint Online и OneDrive для бизнеса

| Цели общего доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Совместное доступ к сайтам и документам внешним пользователям | Администраторы настраивают общий доступ на уровне клиента или на уровне коллекции веб-сайтов для учетных записей Майкрософт с проверкой подлинности, учетных записей для работы или учебных учетных записей с проверкой подлинности или гостевых учетных записей |  <ul><li> [Управление внешним доступом для среды SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Ограничение общего доступа к содержимому SharePoint и OneDrive по домену](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) </li><li> [Использование SharePoint Online в качестве решения экстрасети "бизнес-бизнес" (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Отслеживание и контроль внешнего общего доступа для конечных пользователей | Владельцы файлов OneDrive для бизнеса и конечные пользователи SharePoint Online настраивают общий доступ к сайтам и документам, а также устанавливают уведомления для отслеживания общего доступа |  <ul><li> [Настройка уведомлений для внешнего общего доступа для OneDrive для бизнеса](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Общий доступ к файлам и папкам SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Варианты совместной работы Skype для бизнеса

| Цель совместного доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Skype для бизнеса Online : мгновенные звонки, звонки и присутствие с другими пользователями Skype для бизнеса | Администраторы могут включить для своих пользователей Skype для бизнеса Online мгновенные звонки, аудио- и видеозвонки и видеть присутствие с пользователями в другом клиенте Microsoft 365. | [Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype для бизнеса Online : мгновенные звонки, звонки и присутствие пользователей Skype (потребителей) | Администраторы могут включить для своих пользователей Skype для бизнеса Online мгновенные звонки, звонить и видеть присутствие пользователей Skype (потребителей). | [Разрешение на добавление контактов Skype пользователям Skype для бизнеса](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Варианты совместной работы Azure AD B2B

| Цель совместного доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Совместная работа Azure AD B2B — общий доступ к контенту путем добавления внешних пользователей в группу в каталоге организации | Глобальный администратор одного клиента Microsoft 365 может приглашать пользователей из другого клиента Microsoft 365 присоединиться к своим каталогам, добавить этих внешних пользователей в группу и предоставить доступ к контенту, например сайтам и библиотекам SharePoint для группы. |  <ul><li> [Что такое предварительная версия совместной работы Azure AD B2B?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: новые обновления делают кросс-бизнес-collab простым](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Внешний общий доступ и совместная работа Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [API совместной работы и настройка Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD и демонстрация удостоверений: совместная работа Azure AD B2B (для бизнеса и бизнеса)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Варианты совместной работы Microsoft 365

| Цель совместного доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Группы Microsoft 365: электронная почта, календарь, OneNote и общие файлы в централизованном месте | Группы поддерживаются в планах Business Essentials, Business Premium, Education и Enterprise E1, E3 и E5. Пользователи в одном клиенте Microsoft 365 могут создавать группы и приглашать пользователей из другого клиента Microsoft 365 в качестве гостевых пользователей. Применимо и к Dynamics CRM. |  <ul><li> [Сведения о группах Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Гостевой доступ в группах Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Развертывание групп Microsoft 365](https://technet.microsoft.com/library/dn896591.aspx) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Варианты совместной работы в Yammer

| Цель совместного доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Yammer : совместная работа с помощью корпоративной социальной среды | Если администратор Yammer не отключает возможность создания внешних групп, пользователи могут создавать внешние группы для совместной работы в Yammer посредством бесед, а также для публикаций, обмена файлами и чата в Интернете. | [Создание внешних групп в Yammer и управление ими](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Варианты совместной работы Teams

|Цель совместного доступа|Административное действие|Сведения о том, как это сделать|
|:-----|:-----|:-----|
|Совместное взаимодействие в Teams с внешними пользователями в организации | Глобальный администратор приглашенного клиента Microsoft 365 должен включить внешнюю совместную работу в Teams. Глобальные администраторы и владельцы команд теперь смогут приглашать всех, у кого есть адрес электронной почты, для совместной работы в Teams.  <br/> Администраторы также могут управлять гостями и редактировать их, уже присутствующие в клиенте. |  <ul><li> [Авторизировать гостевой доступ](https://docs.microsoft.com/microsoftteams/teams-dependencies) </li><li> [Включить или отключить гостевой доступ в Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) </li><li> [Управление гостевим доступом с помощью PowerShell](https://docs.microsoft.com/microsoftteams/guest-access-powershell) </li><li> [Контрольный список гостевого доступа](https://docs.microsoft.com/microsoftteams/guest-access-checklist) </li><li> [Просмотр гостевых пользователей](https://docs.microsoft.com/microsoftteams/view-guests) </li><li> [Изменение сведений о гостевых пользователях](https://docs.microsoft.com/microsoftteams/edit-guests-information) </li></ul> |
|Владельцы команд могут приглашать и управлять взаимодействием гостей в своих командах.  |Владельцы команд имеют дополнительные средства контроля над тем, что могут делать гости в своих командах. |  <ul><li> [Добавление гостей](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Добавление гостя в команду](https://docs.microsoft.com/microsoftteams/add-guests) </li><li> [Управление гостевых доступом в Teams](https://docs.microsoft.com/microsoftteams/manage-guests) </li><li> [See who's on a Team or in a Channel](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Гости из других клиентов могут просматривать содержимое в Teams и совместно работать с другими участниками | Нет. | [Гостевой доступ](https://docs.microsoft.com/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Варианты совместной работы Power BI

| Цель совместного доступа | Административное действие | Сведения о том, как это сделать |
|:-----|:-----|:-----|
|Power BI позволяет внешним гостевых пользователям использовать общий для них контент по ссылкам. Это позволяет пользователям организации безопасно распространять контент в разных организациях.<br/> | Администратор Power BI может контролировать, могут ли пользователи приглашать внешних пользователей для просмотра контента в организации.| [Распространение контента Power BI среди внешних гостевых пользователей с помощью Azure AD B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Указывает на то, что следует знать о совместной работе между клиентами Microsoft 365

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Общий доступ к учетным записям пользователей, лицензиям, подпискам и хранилищу

Каждая организация имеет собственные учетные записи пользователей, удостоверения, группы безопасности, подписки, лицензии и хранилище. Сотрудники используют функции совместной работы в Microsoft 365 вместе с политиками общего доступа и настройками безопасности для предоставления доступа к необходимой информации, сохраняя контроль над активами компании.
  
- **Учетные записи пользователей:** Учетные записи нельзя совместно использовать или дублировать между арендаторами или разделами в локальной службе доменов Active Directory. 
    
- **Подписки &amp;** на лицензии: в Microsoft 365 лицензии из планов лицензирования (также называемые планами SKUs или Microsoft 365) дают пользователям доступ к службам Microsoft 365, определенным для этих планов. 
    
- **Хранилище:** В планах лицензирования Microsoft 365 ограничения на программное обеспечение для SharePoint Online управляются отдельно от ограничений хранилища почтовых ящиков. Ограничения хранилища почтовых ящиков устанавливаются и управляются с помощью Exchange Online. В обоих случаях хранилище не может быть общим для всех клиентов. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Можно ли совместно использовать пространства доменных имен в клиентах Microsoft 365?

Нет. Доменные имена организаций, например fabrikam.com или tailspintoys.com, можно связывать и использовать только с одним клиентом Microsoft 365. У каждого клиента должно быть собственное пространство имен. Пространства имен UPN, SMTP и SIP нельзя совместно использовать для разных клиентов.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Как насчет гибридных компонентов и совместной работы между клиентами Microsoft 365?

Гибридные компоненты локальной организации, такие как организация Exchange и Azure AD Connect, нельзя разделить на несколько клиентов.
 

