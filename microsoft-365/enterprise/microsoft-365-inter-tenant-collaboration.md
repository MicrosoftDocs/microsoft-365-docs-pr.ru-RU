---
title: Microsoft 365 совместной работы с клиентом
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
description: Узнайте, как Microsoft 365 совместной работы между арендаторами и организациями, что позволяет различным организациям безопасно работать вместе.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4ff55d9bc355a03e7f7336bd01d3c19a60d2d31
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923282"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 совместной работы с клиентом

Предположим, что две организации, Fabrikam и Contoso, имеют Microsoft 365 бизнес-клиента и они хотят работать вместе над несколькими проектами; некоторые из которых работают в течение ограниченного времени, а некоторые из них продолжаются. Как Fabrikam и Contoso позволяют своим людям и командам более эффективно взаимодействовать с различными Microsoft 365 клиентов безопасным образом? Microsoft 365 совместной работы Azure Active Directory (Azure AD) B2B предоставляет несколько вариантов. В этой статье описано несколько ключевых сценариев, которые могут рассматривать Fabrikam и Contoso.
  
Microsoft 365 взаимодействия между арендаторами включают использование центрального расположения для файлов и бесед, общий доступ к календарям, использование чата, аудио- и видеозвонков для связи и обеспечение доступа к ресурсам и приложениям. Используйте следующие таблицы для выбора решений и получения дополнительных данных.
  
## <a name="exchange-online-collaboration-options"></a>Exchange Online совместной работы

| Цель совместного доступа | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Делитесь календарями с другой Microsoft 365 организацией |Администраторы могут настроить различные уровни доступа к календарю в Exchange Online, чтобы позволить предприятиям сотрудничать с другими предприятиями и позволять пользователям делиться расписаниями (бесплатными и загруженными сведениями) с другими. | <ul><li>[Общий доступ](/exchange/sharing/sharing) </li><li> [Связи организации](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [Создание связи организации](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Изменение отношения организации ](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [Удаление связи организации](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [Совместное использование календарей с внешними пользователями](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Управление тем, как пользователи делятся своими календарями с людьми за пределами организации | Администраторы применяют политики общего доступа к почтовым ящикам пользователей, чтобы контролировать, с кем можно обмениваться данными, и с уровнем предоставленного доступа. |  <ul><li> [Политики общего доступа](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [Создание политики общего доступа](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [Применение политики общего доступа к почтовым ящикам](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [Изменение, отключение или удаление политики общего доступа](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|Настройка безопасных каналов электронной почты и управление потоком почты с организациями-партнерами | Администраторы создают соединители для применения безопасности к почтовым биржам с организацией-партнером или поставщиком услуг. Соединительные устройства используют шифрование с помощью безопасности транспортного слоя (TLS), а также позволяют вводить ограничения на доменные имена или IP-адреса, от которых партнеры отправляют электронную почту. |  <ul><li> [Использование протокола TLS службой Exchange Online для защиты электронной почты](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [Настройка потока обработки почты с помощью соединителя](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [Удаленные домены](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [Настройка соединитетеля для безопасного потока почты в организации-партнере](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [Лучшие практики потока почты (обзор)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Варианты совместной OneDrive для бизнеса и OneDrive для бизнеса в Интернете

| Общий доступ к целям | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Совместное доступ к сайтам и документам с внешними пользователями | Администраторы настраивают общий доступ на уровне клиента или на уровне коллекции сайтов для проверки подлинности учетной записи Майкрософт, проверки подлинности учетных записей или учетных записей гостей. |  <ul><li> [Управление внешним доступом для среды SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Ограничение общего доступа к контенту SharePoint и OneDrive по домену](/sharepoint/restricted-domains-sharing) </li><li> [Использование SharePoint Online в качестве решения экстрасети для бизнеса (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Отслеживание и управление внешним доступом для конечных пользователей | OneDrive для бизнеса и конечные пользователи SharePoint Сети настраивают общий доступ к сайтам и документам и устанавливают уведомления для отслеживания общего доступа |  <ul><li> [Настройка уведомлений для внешнего общего доступа для OneDrive для бизнеса](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Общий доступ к файлам и папкам SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Skype для бизнеса совместной работы

| Цель совместного доступа | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Skype для бизнеса Online - im, calls, and presence with other Skype для бизнеса users | Администраторы могут включить Skype для бизнеса пользователей Сети в чат, сделать аудио- и видеозвонки и увидеть присутствие с пользователями в другом Microsoft 365 клиенте. | [Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype для бизнеса Online - im, calls, and presence with Skype (consumer) users | Администраторы могут включить Skype для бизнеса пользователей в Интернете в чат, звонить и видеть присутствие Skype (потребителей). | [Разрешение на добавление контактов Skype пользователям Skype для бизнеса](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Параметры совместной работы Azure AD B2B

| Цель совместного доступа | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Совместная работа Azure AD B2B — совместное использование контента путем добавления внешних пользователей в группу в каталоге организации | Глобальный администратор одного клиента Microsoft 365 может пригласить пользователей другого клиента Microsoft 365 присоединиться к каталогу, добавить этих внешних пользователей в группу и предоставить доступ к контенту, например к SharePoint сайтам и библиотекам для группы. |  <ul><li> [Что такое предварительный просмотр совместной работы Azure AD B2B?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: новые обновления удобна для кросс-бизнес-коллаба](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Внешнее совместное Azure Active Directory B2B](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory API совместной работы и настройки B2B](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD and Identity Show: Azure AD B2B Collaboration (Business to Business](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 параметров совместной работы

| Цель совместного доступа | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Microsoft 365 Группы — электронная почта, календарь, OneNote и общие файлы в центре | Группы поддерживаются в планах Business Essentials, Business Premium, Education и Enterprise E1, E3 и E5. Пользователи одного Microsoft 365 могут создавать группу и приглашать людей в другой Microsoft 365 в качестве гостевых пользователей. Применяется и к динамическим CRM. |  <ul><li> [Сведения о группах Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Гостевой доступ в Microsoft 365 группах](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Развертывание Microsoft 365 групп](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Yammer совместной работы

| Цель совместного доступа | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Yammer - Совместная работа с помощью корпоративной социальной среды | Если возможность создания внешних групп не отключена администратором Yammer, пользователи могут создавать внешние группы для совместной работы в Yammer посредством бесед, а также для того, чтобы выполнять публикации, обмениваться файлами и общаться в интернете. | [Создание внешних групп в Yammer и управление ими](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Teams параметров совместной работы

|Цель совместного доступа|Административное действие|Сведения о том, как|
|:-----|:-----|:-----|
|Сотрудничество в Teams с пользователями, внешними для организации | Глобальный администратор для приглашенного клиента Microsoft 365, чтобы включить внешнюю совместную работу в Teams. Глобальные администраторы и владельцы групп теперь смогут приглашать всех, у кого есть электронный адрес, для совместной Teams.  <br/> Администраторы также могут управлять и редактировать гостей, уже присутствующих в их клиенте. |  <ul><li> [Авторизировать гостевой доступ](/microsoftteams/teams-dependencies) </li><li> [Включить или отключить гостевой доступ в Teams](/microsoftteams/set-up-guests) </li><li> [Использование PowerShell для управления гостевим доступом](/microsoftteams/guest-access-powershell) </li><li> [Контрольный список доступа гостей](/microsoftteams/guest-access-checklist) </li><li> [Просмотр гостевых пользователей](/microsoftteams/view-guests) </li><li> [Изменение сведений о гостевых пользователях](/microsoftteams/edit-guests-information) </li></ul> |
|Владельцы групп могут приглашать и управлять взаимодействием гостей в их командах.  |Владельцы групп имеют дополнительные элементы управления тем, что гости могут делать в своих командах. |  <ul><li> [Добавление гостей](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Добавление гостя в команду](/microsoftteams/add-guests) </li><li> [Управление гостевых доступов в Teams](/microsoftteams/manage-guests) </li><li> [Узнайте, кто в команде или в канале](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Гости из других клиентов могут просматривать содержимое в Teams и сотрудничать с другими участниками | Нет. | [Возможность доступа к гостю](/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Power BI совместной работы

| Цель совместного доступа | Административное действие | Сведения о том, как |
|:-----|:-----|:-----|
|Power BI позволяет внешним гостевых пользователям потреблять общий для них контент по ссылкам. Это позволяет пользователям организации безопасно распространять контент между организациями.<br/> | Администратор Power BI, могут ли пользователи приглашать внешних пользователей для просмотра контента в организации.| [Распространение Power BI для внешних гостевых пользователей с помощью Azure AD B2B](/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Указывает, что следует знать о Microsoft 365 совместной работы с клиентом

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Общий доступ к учетным записям пользователей, лицензиям, подпискам и хранению

Каждая организация поддерживает собственные учетные записи пользователей, удостоверения, группы безопасности, подписки, лицензии и хранилище. Люди используют функции совместной Microsoft 365 совместном использовании политик и параметров безопасности для предоставления доступа к необходимой информации при сохранении контроля над активами компании.
  
- **Учетные записи пользователей:** Учетные записи не могут быть общими или дублироваться между арендаторами или разделами в локальной службе домена Active Directory. 
    
- **Подписки &amp;** на лицензии: в Microsoft 365 лицензии из планов лицензирования (также называемых SKUs или Microsoft 365 планов) дают пользователям доступ к Microsoft 365 службы, которые определены для этих планов. 
    
- **служба хранилища:** В Microsoft 365 планах лицензирования границы и ограничения программного обеспечения для SharePoint Online управляются отдельно от ограничений хранения почтовых ящиков. Ограничения хранения почтовых ящиков устанавливаются и управляются с помощью Exchange Online. В обоих сценариях хранение не может быть общим для всех клиентов. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Можем ли мы обмениваться пространствами доменных имен Microsoft 365 клиентов?

Нет. Имена доменов организации, такие как fabrikam.com или tailspintoys.com, можно связывать и использовать только с одним Microsoft 365 клиентом. Каждый клиент должен иметь свое пространство имен. Пространства имен UPN, SMTP и SIP не могут быть общими для всех клиентов.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Как насчет гибридных компонентов и Microsoft 365 совместной работы с клиентом?

Локально гибридные компоненты, такие как Exchange и Azure AD Подключение, не могут быть разделены между несколькими клиентами.
