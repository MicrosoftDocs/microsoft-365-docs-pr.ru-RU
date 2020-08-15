---
title: Совместная работа Microsoft 365 между клиентами
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/08/2018
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
description: Узнайте, как совместная работа Microsoft 365 работает между клиентами и организациями, позволяя различным организациям безопасно работать вместе.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 529d4a320fe9aefa5d1ddfbac56742991dbd732d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693295"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Совместная работа Microsoft 365 между клиентами

В этой статье описывается несколько способов совместной совместной работе между двумя клиентами Microsoft 365. Он предназначен для администраторов Microsoft 365.
  
Предположим, что у двух организаций, Fabrikam и Contoso, у каждого из них есть клиент Microsoft 365 для бизнеса, и они хотят совместно работать над несколькими проектами; Некоторые из них работают в течение ограниченного периода времени, а некоторые — в некоторых из них. Как компания Fabrikam и компания Contoso разрешите своим людям и Teams эффективнее сотрудничать в разных клиентах Microsoft 365? Microsoft 365 в сочетании с совместной работой Azure Active Directory B2B предоставляет несколько вариантов. В этой статье описываются несколько ключевых сценариев, которые могут учитывать Fabrikam и contoso.
  
Возможности совместной работы в Microsoft 365 включают в себя централизованное расположение файлов и бесед, общий доступ к календарям, использование обмена мгновенными сообщениями, аудио-и видеовызовов для общения и обеспечение безопасности доступа к ресурсам и приложениям. Используйте приведенные ниже таблицы для выбора решений и дополнительных сведений.
  
## <a name="exchange-online-collaboration-options"></a>Параметры совместной работы в Exchange Online

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Совместное использование календарей с другой организацией Microsoft 365  <br/> |Администраторы могут настроить различные уровни доступа к календарю в Exchange Online, чтобы позволить предприятиям совместно работать с другими организациями, а также предоставить пользователям общий доступ к расписаниям (сведения о доступности) другим пользователям.  <br/> |[Общий доступ в Exchange Online](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) <br/> [Связи Организации в Exchange Online](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) <br/> [Создание связи организации в Exchange Online](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) <br/> [Изменение и связь организации в Exchange Online](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) <br/> [Удаление связи организации в Exchange Online](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) <br/> [Совместное использование календарей с внешними пользователями](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) <br/> |
|Управление совместным доступом пользователей к календарям для людей за преличной Организацией  <br/> |Администраторы применяют политики общего доступа к почтовым ящикам пользователей, чтобы контролировать, к кому им можно предоставить общий доступ, и уровень предоставляемых разрешений.  <br/> |[Политики общего доступа в Exchange Online](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) <br/> [Создание политики общего доступа в Exchange Online](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) <br/> [Применение политики общего доступа к почтовым ящикам в Exchange Online](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) <br/> [Изменение, отключение или удаление политики общего доступа в Exchange Online](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) <br/> |
|Настройка безопасных каналов электронной почты и управление процессом обработки почты с помощью партнерских организаций  <br/> |Администраторы создают соединители для применения безопасности к почтовым обменам с партнерской организацией или поставщиком услуг. Соединители обеспечивают шифрование с помощью протокола TLS, а также обеспечивают ограничения для доменных имен или диапазонов IP-адресов, с которых ваши партнеры отправляют электронную почту.  <br/> |[Использование протокола TLS для защиты подключений электронной почты в Exchange Online](https://technet.microsoft.com/library/mt163898.aspx) <br/> [Настройка почтового процесса с помощью соединителей](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) <br/> [Удаленные домены в Exchange Online](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) <br/> [Настройка соединителя для безопасного обмена почтой с партнерской организацией](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) <br/> [Рекомендации по использованию почтового процесса для Exchange Online (обзор)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) <br/> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Параметры совместной работы в SharePoint Online и OneDrive для бизнеса

|**Цели общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Совместное использование сайтов и документов с внешними пользователями  <br/> |Администраторы настраивают общий доступ на уровне клиента или семейства веб-сайтов для проверки подлинности учетной записи Майкрософт, рабочей или учебной учетной записи, а также учетных записей гостя.  <br/> |[Управление внешним доступом для среды SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> [Ограничение общего доступа к контенту SharePoint и OneDrive по доменам](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) <br/> [Использование SharePoint Online в качестве решения для экстрасети "бизнес-бизнес" (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) <br/> |
|Отслеживание внешнего общего доступа для конечных пользователей и управление им  <br/> |Владельцы файлов OneDrive для бизнеса и пользователи SharePoint Online настраивают общий доступ к сайтам и документам и устанавливать уведомления для отслеживания общего доступа  <br/> |[Настройка уведомлений для внешнего общего доступа в OneDrive для бизнеса](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) <br/> [Общий доступ к файлам и папкам SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) <br/> |
   
## <a name="skype-for-business-collaboration-options"></a>Варианты совместной работы в Skype для бизнеса

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Skype для бизнеса Online — обмен мгновенными сообщениями, звонки и присутствие с другими пользователями Skype для бизнеса  <br/> |Администраторы могут разрешить пользователям Skype для бизнеса Online обмениваться мгновенными сообщениями, совершать аудио-и видеовызовы, а также просматривать сведения о присутствии для пользователей в другом клиенте Microsoft 365.  <br/> |[Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94) <br/> |
|Skype для бизнеса Online — обмен мгновенными сообщениями, звонки и присутствие с пользователями Skype (потребителем)  <br/> |Администраторы могут разрешить пользователям Skype для бизнеса Online обмениваться мгновенными сообщениями, совершать звонки и просматривать сведения о присутствии с пользователями Skype (потребителем).  <br/> |[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460) <br/> |
   
## <a name="azure-ad-b2b-collaboration-options"></a>Возможности совместной работы в Azure AD B2B

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Совместная работа Azure AD B2B — общий доступ к контенту путем добавления внешних пользователей в группу в каталоге Организации.  <br/> |Глобальный администратор одного клиента Microsoft 365 может приглашать пользователей в другом клиенте Microsoft 365 для присоединения к каталогу, добавления этих внешних пользователей в группу и предоставления доступа к содержимому, например сайтам и библиотекам SharePoint для группы.  <br/> |[Что такое предварительный просмотр совместной работы Azure AD B2B?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) <br/> [Azure AD B2B: новые обновления делают коллаб простыми](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) <br/> [Внешний общий доступ и совместная работа Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) <br/> [API совместной работы и настройка Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) <br/> [Покажите Azure AD и удостоверения: совместная работа Azure AD B2B (бизнес для бизнеса)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) <br/> |
   
## <a name="microsoft-365-collaboration-options"></a>Параметры совместной работы Microsoft 365

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Группы Microsoft 365: Электронная почта, календарь, OneNote и общие файлы в центральном расположении  <br/> |Группы поддерживаются в планах бизнеса, бизнеса премиум, в образовании, а также в планах для предприятий E1, E3 и в/в. Пользователи в одном клиенте Microsoft 365 могут создать группу и пригласить людей в другом клиенте Microsoft 365 как гостей. Применяется также к Dynamics CRM.  <br/> |[Сведения о группах Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) <br/> [Гостевой доступ в группах Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) <br/> [Развертывание групп Microsoft 365](https://technet.microsoft.com/library/dn896591.aspx) <br/> |
   
## <a name="yammer-collaboration-options"></a>Параметры совместной работы в Yammer

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Совместная работа в Yammer через корпоративный социальный носитель  <br/> |Если администратор Yammer не может создавать внешние группы, то пользователи могут создавать внешние группы для совместной работы в Yammer с помощью бесед, а также включать и отключать публикации, обмениваться файлами и общаться в Интернете.  <br/> |[Создание внешних групп в Yammer и управление ими](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a) <br/> |
   
## <a name="teams-collaboration-options"></a>Параметры совместной работы в Teams

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Совместное сотрудничество в Teams с пользователями, внешними по отношению к Организации  <br/> |Глобальный администратор для приглашения клиенту Microsoft 365 необходимо включить внешнюю совместную работу в Teams. Глобальные администраторы и владельцы групп теперь могут приглашать всех пользователей с адресом электронной почты для совместной работы в Teams.  <br/> Администраторы также могут управлять гостями, уже присутствующими в своем клиенте, а также изменять их.  <br/> |[Авторизация гостевого доступа](https://docs.microsoft.com/microsoftteams/teams-dependencies) <br/> [Включение и отключение гостевого доступа в Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) <br/> [Использование PowerShell для управления гостевым доступом](https://docs.microsoft.com/microsoftteams/guest-access-powershell) <br/> [Контрольный список гостевого доступа](https://docs.microsoft.com/microsoftteams/guest-access-checklist) <br/> [Просмотр гостевых пользователей](https://docs.microsoft.com/microsoftteams/view-guests) <br/> [Изменение сведений о гостевых пользователях](https://docs.microsoft.com/microsoftteams/edit-guests-information) <br/> |
|Владельцы групп могут приглашать и управлять тем, как гости совместно работают в своих командах.  <br/> |Владельцы команды имеют дополнительные элементы управления, которые могут выполнять гости в своих командах.  <br/> |[Добавление гостей](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) <br/> [Добавление гостя в команду](https://docs.microsoft.com/microsoftteams/add-guests) <br/> [Управление гостевым доступом в Teams](https://docs.microsoft.com/microsoftteams/manage-guests) <br/> [Узнайте, кто входит в группу или в канал](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> |
|Гости из других клиентов могут просматривать содержимое в Teams и совместно работать с другими участниками.  <br/> |Нет.  <br/> |[Интерфейс гостевого доступа](https://docs.microsoft.com/microsoftteams/guest-experience) <br/> |

## <a name="power-bi-collaboration-options"></a>Параметры совместной работы Power BI

|**Цель общего доступа**|**Административное действие**|**Инструкции**|
|:-----|:-----|:-----|
|Power BI позволяет внешним гостевым пользователям получать доступ к контенту через ссылки. Это позволяет пользователям в Организации распространять контент безопасным способом в разных организациях.<br/> | Администратор Power BI может управлять тем, могут ли пользователи приглашать внешних пользователей для просмотра контента в Организации. <br/> |[Распространение контента Power BI внешним гостевым пользователям с помощью Azure AD B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) <br/> |
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Сведения о совместной работе Microsoft 365 между клиентами

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Совместное использование учетных записей пользователей, лицензий, подписок и хранилища

Каждая организация поддерживает свои учетные записи пользователей, удостоверения, группы безопасности, подписки, лицензии и хранилище. Люди используют функции совместной работы в Microsoft 365 вместе с политиками общего доступа и параметрами безопасности для предоставления доступа к необходимой информации при управлении ресурсами компании.
  
- **Учетные записи пользователей:** Учетные записи нельзя дублировать между клиентами или разделами в локальной службе каталогов Active Directory. 
    
- **Подписки на лицензии &amp; :** в Microsoft 365 лицензии из планов лицензирования (также называемых конфигурациями и планами Microsoft 365) предоставляют пользователям доступ к службам Microsoft 365, определенным для этих планов. 
    
- **Хранилище:** В планах Microsoft 365 программные границы и ограничения для SharePoint Online управляются отдельно от ограничений хранилища почтовых ящиков. Пределы хранилища почтовых ящиков настраиваются и управляются с помощью Exchange Online. В обоих сценариях хранилище не может совместно использоваться несколькими клиентами. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Можно предоставить общий доступ к пространствам имен доменов для клиентов Microsoft 365?

Нет. Домены запоминающийся, такие как fabrikam.com и tailspintoys.com, могут быть связаны и использоваться только с одним клиентом в каждый момент времени. У каждого клиента должно быть собственное пространство имен; UPN, пространства имен SMTP и SIP не могут совместно использоваться несколькими клиентами.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Что делать с гибридными компонентами и совместная работа Microsoft 365 между клиентами?

Локальные Гибридные компоненты, такие как организация Exchange и служба Azure AD Connect, не могут быть распределены между несколькими клиентами.
  

