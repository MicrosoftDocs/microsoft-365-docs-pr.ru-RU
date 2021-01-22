---
title: Предварительная работа по миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Предварительная работа при переходе с Microsoft Cloud в Германии (Microsoft Cloud Deutschland) на службы Office 365 в новом регионе центра обработки данных в Германии.
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921570"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Предварительная работа по миграции из Microsoft Cloud Deutschland


Используйте эти ссылки для получения предварительных действий, необходимых для вашей организации:

- Для всех подписок сделайте [вот что.](#applies-to-everyone)
- Если вы используете Exchange Online или гибридную сеть Exchange, сделайте [это.](#exchange-online)
- Если вы используете SharePoint Online, сделайте [это.](#sharepoint-online)
- Если вы используете стороне решение для управления мобильными устройствами (MDM), сделайте [это.](#mobile)
- Если вы используете сторонние службы или бизнес-приложения, интегрированные с Office 365, сделайте [это.](#line-of-business-apps)
- Если вы также используете службы Azure помимо служб, включенных в подписку на Office 365, сделайте [это.](#azure)
- Если вы также используете Dynamics 365, сделайте [это.](#dynamics365)
- Если вы также используете Power BI, сделайте [это.](#power-bi)
- Для изменений DNS сделайте [это.](#dns)
- Если вы используете федератное удостоверение, сделайте [это.](#federated-identity)

## <a name="applies-to-everyone"></a>Применимо ко всем

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Обеспечение сетевого подключения к URL-адресам и IP-адресам служб [Office 365.](https://aka.ms/o365urls) | Все клиенты и службы, используемые клиентом для доступа к службе Office 365, должны иметь доступ к конечным точкам служб Office 365. | Все переносимые клиенты и клиенты с доступом к сети ограничены Microsoft Cloud Deutschland. | Обязательное действие. Бездействие может привести к сбоям службы или клиентского программного обеспечения. |
| Просмотрите и подготовьтесь к изменениям DNS, связанным с миграцией. | Клиент подготавливает записи DNS для Exchange Online и Exchange Online Protection (запись MX и т. д.). | Клиенты Exchange Online | Это рекомендуемое действие. Никакие действия не означает, что электронная почта перенесенных клиентов может проходить через Microsoft Cloud Deutschland, пока службы Microsoft Cloud Deutschland не будут отключены. |
| Просмотрите и подготовьтесь к изменениям DNS, связанным с миграцией. | Изменения в зоне DNS, владельцем клиента, для Skype для бизнеса Online. | Клиенты Skype для бизнеса Online | - Рекомендуется обновить срок жизни (TTL) для записей DNS любого домена клиента до 5 минут, чтобы ускорить обновление записей DNS. Однако переключение под управлением Майкрософт, связанное с этим изменением DNS, может произойти в любое время в течение предоставленного 24-часового окна изменения. <br><br> - В будущем возможно прерывать обслуживание. Пользователи не смогут войти в Skype для бизнеса и будут перенаправлены на перенесенный опыт Teams в службах Office 365. |
| Подготовка обучения и подготовки конечных пользователей и администрирования к переходу на Microsoft Teams. | Для успешного перехода со Skype на Teams спланируя взаимодействие и готовность пользователей. | Клиенты Skype для бизнеса Online | - Клиенты должны знать о новых службах и о том, как их использовать после перехода на службы Office 365. <br><br> - После внесения изменений в DNS для доменов клиентов и первоначального домена пользователи будут входить в Skype для бизнеса и видеть, что теперь они перенесены в Teams. Это также позволит скачать настольный клиент для Teams в фоновом режиме. |
| Подготовка обучения пользователей и администрирования по удаляемой и повторной добавлению учетной записи в Microsoft Outlook для iOS и Android. | Учетные записи Microsoft Outlook для iOS и Android, настроенные с почтовыми ящиками в Microsoft Cloud Deutschland, могут быть удалены и добавлены в Outlook повторно, чтобы правильно синхронизировать новую конфигурацию служб Office 365. | Пользователи Microsoft Outlook для iOS и Android | Почтовые ящики Outlook, настроенные ранее для Microsoft Cloud Deutschland, могут не получить новую конфигурацию служб Office 365, что может привести к ошибкам и ухудшению производительности других пользовательских функций. ИТ-администраторам рекомендуется предоставить документацию, которая заблаговременно предписывает пользователям удалять и повторно добавлять свои учетные записи в Microsoft Outlook для iOS и Android, если после миграции возникают проблемы с входом или синхронизацией почты. |
| Подготовьтесь к тому, чтобы уведомить пользователей о перезапуске и входе в свои клиенты и выходе из них после миграции. | В процессе миграции клиентские лицензии Office будут перенамеряться из Microsoft Cloud Deutschland в службы Office 365. Клиенты выбирают новую действительную лицензию после того, как вы выходите и в клиенты Office. | Клиенты приложений Microsoft 365 |  Продукты Office пользователей должны обновлять лицензии из служб Office 365. Если лицензии не обновлены, в продуктах Office могут возникнуть ошибки проверки лицензий. |
| Отмените все пробные подписки. | Пробные подписки не будут перенесены и будут блокировать передачу платных подписок. | Все клиенты | Срок действия пробных служб истекает и они не работают, если пользователи получили доступ после отмены. |
| Развертывание настольного клиента Teams для пользователей, которые имеют доступ к Skype для бизнеса в Германии. | Миграция перемещает пользователей в Teams для совместной работы, звонков и чата. Либо развернем настольный клиент Teams, либо убедитесь, что доступен поддерживаемый браузер. | Клиенты Skype для бизнеса | Бездействие приведет к недоступности служб совместной работы Teams. |
| Анализ различий в лицензионных функциях между Microsoft Cloud Deutschland и службами Office 365. | Службы Office 365 включают дополнительные функции и службы, недоступные в текущем Microsoft Cloud Deutschland. Во время передачи подписки пользователям будут доступны новые функции. | Все клиенты | - Проанализируйте различные функции, предоставляемые лицензиями для Microsoft Cloud Deutschland и служб Office 365. Начните с описания [служб платформы Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) <br><br> - Определите, следует ли изначально отключить какие-либо новые функции служб Office 365, чтобы ограничить влияние на пользователей или на управление изменениями пользователей, и при необходимости изменить назначения лицензий пользователей. <br><br> – Подготовьте пользователей и сотрудников службы поддержки к новым службам и функциям, предоставляемым службами Office 365. |
| Создайте политики хранения [для всей организации,](https://docs.microsoft.com/microsoft-365/compliance/retention) чтобы защититься от случайного удаления контента во время миграции.  | - Чтобы конечные пользователи не случайно удалили контент во время миграции, клиенты могут включить политику хранения для всей организации. <br><br> - Хотя хранение не требуется, так как удержания, размещенные в любое время во время миграции, должны работать ожидаемым образом, наличие политики хранения является механизмом обеспечения безопасности для работы системы. В то же время политика хранения может использоваться не всеми клиентами, особенно теми, кто заинтересован в чрезмерном сохранении. | Клиенты Office | Применение политики хранения, как описано в описании [политик хранения и меток хранения.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) |
| [Резервное копирование фермы служб федерации Active Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) для сценариев аварийного восстановления. | Клиенты должны соответствующим образом сохранять ферму AD FS, чтобы гарантировать восстановление доверия с отношениями с отношениями с & в Германии, не затрагивая URI доменов, выдавающих эти домены. Корпорация Майкрософт рекомендует при необходимости использовать быстрое восстановление AD FS для резервного копирования фермы и соответствующего восстановления. | Федерационные организации проверки подлинности | Обязательное действие. Бездействие приведет к влиянию службы во время миграции, если ферма AD FS клиента не будет работать. |


## <a name="exchange-online"></a>Exchange Online

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Уведомите внешних партнеров о предстоящем переходе на службы Office 365. | Конфигурации адресного пространства доступности позволяют обмениваться сведениями о доступности с Office 365. | Пользователи Exchange Online, которые включили общий доступ к календарю и адресному пространству доступности. | Обязательное действие.  Невыполнение этого может привести к сбою службы или клиента на более позднем этапе миграции клиента. |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>Для гибридной системы Exchange

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Удалить предыдущие версии мастера гибридной конфигурации (HCW), а затем установить и выполнить последнюю версию, 17.0.5378.0, из [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | Последняя версия HCW включает необходимые обновления для поддержки клиентов, которые переходят с Microsoft Cloud Deutschland на службы Office 365. <br><br> Обновления включают изменения в параметрах локального сертификата для соединителю отправки и получения. | Клиенты Exchange Online, работающие с гибридным развертыванием | Обязательное действие. Невыполнение этого может привести к сбою службы или клиента. |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

Если у вас есть SharePoint 2013:

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Ограничить рабочий процесс SharePoint 2013, использовать во время миграции SharePoint Online. | Уменьшите количество процессов SharePoint 2013 и завершите их перед переходами. | Клиенты SharePoint Online | Бездействие может привести к путанице пользователей и вызовам службы поддержки. |
|||||

## <a name="mobile"></a>Для мобильных устройств

Если вы используете стороне решение для управления мобильными устройствами (MDM):

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Определите, требуется ли после миграции какие-либо перенастройки. | Решения MDM могут быть нацелены `outlook.de` на конечные точки. При переходе на службы Office 365 профили клиентов должны обновляться до URL-адреса служб Office 365. `outlook.office365.com` | Клиенты Exchange Online и MDM | Клиенты могут продолжать работать, пока конечная точка доступна, но они перестанут работать, если конечные точки `outlook.de` Microsoft Cloud Deutschland будут недоступны. |
|||||

## <a name="line-of-business-apps"></a>Бизнес-приложения

Если вы используете сторонние службы или бизнес-приложения, интегрированные с Office 365: 

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Определите, требуется ли после миграции какие-либо перенастройки. | Сторонние службы и приложения, которые интегрируются с Office 365, могут быть закодироваться для того, чтобы ожидать IP-адреса и URL-адреса Microsoft Cloud Deutschland. | Все клиенты | Обязательное действие. Бездействие может привести к сбоям службы или клиентского программного обеспечения. |
|||||

## <a name="azure"></a>Azure 

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Определите, какие службы Azure используются, и подготовьтесь к будущей миграции из Германии в клиент служб Office 365, работая с партнерами. Выполните действия, описанные в книге [о миграции Azure.](https://docs.microsoft.com/azure/germany/germany-migration-main) | Перенос ресурсов Azure отвечает за клиента и требует ручных усилий, следуя предписанным шагам. Понимание того, какие службы используются в организации, является ключевым фактором успешной миграции служб Azure. <br><br> Клиенты Office 365 Germany, у которых есть подписки Azure в одном и том же разделе удостоверений (организации), должны соблюдать предписанный Корпорацией Майкрософт порядок, когда они могут начать миграцию подписок и служб. | Клиенты Azure | - У клиентов может быть несколько подписок Azure, каждая из которых содержит инфраструктуру, службы и компоненты платформы. <br><br> - Администраторы должны определить подписки и заинтересованных лиц, чтобы обеспечить возможность оперативной миграции и проверки в рамках этого события миграции. <br><br> Невыполнения миграции этих подписок и компонентов Azure на предписанную временную шкалу повлияет на завершение перехода Office и Azure AD на службы Office 365 и может привести к потере данных.  <br><br> - Уведомление Центра сообщений будет сигнализировать о том, с какой точки может начаться миграция под руководством клиента. |
|||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="dynamics-365"></a>Dynamics 365

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Для подписок на песочницу Dynamics 365 обязательно скачайте производственную среду экземпляра Dynamics SQL из подписки на Dynamics 365 в Microsoft Cloud Deutschland. Последнюю резервную копию необходимо восстановить в песочнице перед миграцией в песочницу. | Для миграции Dynamics 365 требуется, чтобы клиенты обновили среду песочницы с помощью последней производственной базы данных. | Клиенты Microsoft Dynamics | Команда FastTrack поможет клиентам выполнить "сухую" проверку обновления версии с версии 8.x до 9.1.x. |
|||||

## <a name="power-bi"></a>Power BI

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Удаление объектов из подписок Power BI, которые не будут перенесены из Power BI Microsoft Cloud Deutschland в службы Office 365. | Для переноса служб Power BI потребуется действие клиента для удаления определенных артефактов, таких как наборы данных и панели мониторинга. | Клиенты Power BI | Администраторам может потребоваться удалить следующие элементы из своей подписки: <br> - Real-Time данных (например, наборы потоковой передачи или push-данных) <br> - Конфигурация и источник данных локального шлюза данных Power BI |
|||||

## <a name="dns"></a>DNS

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Удалите MSOID, CName из DNS, владельцем клиента, если он существует в любое время перед вырезанием Azure AD. Можно установить срок жизни в 5 минут, чтобы изменения вступили в силу быстро. | Изменения зоны DNS, которые принадлежат клиенту | Клиенты клиентских служб Office | 
|||||

## <a name="federated-identity"></a>Федеративное удостоверение

| Этапы | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Добавьте идентификатор единого входного (SSO) в существующее отношения доверия с отношениями с ней и отключите автоматическое обновление метаданных AD FS. | Перед началом миграции в отношения доверия с отношениями с отправной стороной AD FS необходимо добавить его. Чтобы избежать случайного удаления идентификатора стороны, отключаем автоматическое обновление для обновлений метаданных. <br><br> Запустите эту команду на сервере AD FS: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Федерационные организации проверки подлинности | Обязательное действие. Бездействие приведет к влиянию службы во время миграции.  |
| Создание отношения доверия с отношениями с клиентами для глобальных конечных точек Azure AD. | Клиентам необходимо вручную создать отношения доверия с отношениями доверия с отношениями с клиентами (RPT) для [глобальных конечных](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) точек. Это делается путем добавления нового RPT через GUI путем использования URL-адреса метаданных глобальной федерации, а затем с помощью правил утверждений [RPT Azure AD](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (в справке AD FS) для создания правил утверждений и их импорта в RPT. | Федерационные организации проверки подлинности | Обязательное действие. Бездействие приведет к влиянию службы во время миграции. |
|||||

## <a name="more-information"></a>Дополнительная информация

Начало работы:

- [Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Переход:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [функций](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
