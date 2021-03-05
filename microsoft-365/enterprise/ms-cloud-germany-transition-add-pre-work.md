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
description: Сводка. Предварительная работа при переходе из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в службы Office 365 в новом немецком регионе центра обработки данных.
ms.openlocfilehash: 085630c498cebfea26fb3de975740af17cb73921
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454423"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Предварительная работа по миграции из Microsoft Cloud Deutschland


Используйте эти ссылки, чтобы получить предварительные действия, соответствующие организации:

- Для всех подписок сделайте [эти действия.](#applies-to-everyone)
- Если вы используете гибрид Exchange Online или Exchange, сделайте [этот шаг.](#exchange-online)
- Если вы используете SharePoint Online, сделайте [этот шаг.](#sharepoint-online)
- Если вы используете решение для управления сторонними мобильными устройствами (MDM), сделайте [этот шаг.](#mobile)
- Если вы используете сторонние приложения-службы или бизнес-приложения, интегрированные с Office 365, сделайте [этот шаг.](#line-of-business-apps)
- Если вы также используете службы Azure за пределами служб, включенных в подписку Office 365, сделайте [этот шаг.](#azure)
- Если вы также используете Dynamics 365, сделайте [этот шаг.](#dynamics365)
- Если вы также используете Power BI, сделайте [этот шаг.](#power-bi)
- Для изменений DNS сделайте [этот шаг.](#dns)
- Если вы используете федераную идентификацию, сделайте [эти действия.](#federated-identity)

## <a name="applies-to-everyone"></a>Применяется ко всем

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Обеспечение подключения сети к URL-адресам служб [Office 365 и IP-адресам.](https://aka.ms/o365urls) | Все клиенты и службы, используемые для доступа к службе Office 365, должны иметь доступ к конечным точкам служб Office 365. | Все переходные клиенты и клиенты с доступом к сети, ограниченные Microsoft Cloud Deutschland. | Обязательное действие. Сбои службы или клиентского программного обеспечения могут возникнуть, если это не будет сделано до этапа 4 из 9. |
| Обзор и подготовка к изменениям DNS, связанных с миграцией. | Изменения зоны DNS, которые принадлежат клиентам, для Skype для бизнеса Online. | Клиенты Skype для бизнеса в Интернете | - Мы рекомендуем обновить время до live (TTL) для записей DNS домена, которые принадлежат клиенту, до 5 минут, чтобы ускорить обновление записей DNS. Однако управляемый Microsoft переключение, связанный с этим изменением DNS, может происходить в любое время в течение предоставленного 24-часового окна изменения. <br><br> — В будущем возможны сбои в работе службы. Пользователи не смогут войти в Skype для бизнеса и будут перенаправлены на перенесенный опыт Teams в службах Office 365. |
| Подготовка подготовки конечных пользователей и администрирования и готовность к переходу в Microsoft Teams. | Будьте успешными при переходе из Skype в Teams, планируя общение с пользователями и готовность. | Клиенты Skype для бизнеса в Интернете | - Клиенты должны знать о новых службах и о том, как использовать их после перехода на службы Office 365. <br><br> - После изменения DNS как для доменов тщеславия клиентов, так и для первоначального домена, пользователи будут подписываться в Skype для бизнеса и видеть, что они теперь перенесены в Teams. Кроме того, в фоновом режиме будет скачивать настольный клиент teams. |
| Подготовка обучения пользователей и администрирования об удалении и повторном добавлении учетной записи в Microsoft Outlook для iOS и Android. | Microsoft Outlook для учетных записей iOS и Android, настроенных с почтовыми ящиками в Microsoft Cloud Deutschland, возможно, придется удалить и снова добавить в Outlook, чтобы правильно синхронизировать новую конфигурацию служб Office 365. | Microsoft Outlook для пользователей iOS и Android | Почтовые ящики Outlook, настроенные ранее для Microsoft Cloud Deutschland, могут не выбирать новую конфигурацию служб Office 365, что приводит к ошибкам и ухудшению производительности других пользовательских интерфейсов. ИТ-администраторам рекомендуется предоставлять документацию, которая предписывает пользователям удалять и повторно добавлять свои учетные записи в Microsoft Outlook для iOS и Android, если после миграции возникают проблемы с входом или синхронизацией почты. |
| Подготовка к оповещению пользователей о перезапуске и входе в клиенты после миграции. | Лицензирование клиентов Office будет переходом из Microsoft Cloud Deutschland в службы Office 365 в процессе миграции. Клиенты выбирают новую действительная лицензия после регистрации в Office и в нее. | Клиенты Приложений Microsoft 365 |  Продукты Office пользователей должны обновлять лицензии служб Office 365. Если лицензии не обновляются, продукты Office могут испытывать ошибки проверки лицензии. |
| Отмена пробных подписок. | Пробные подписки не будут перенесены и будут блокировать передачу платных подписок. | Все клиенты | Пробные службы истекают и не функционируют, если к ним после отмены будут доступны пользователи. |
| Развертывание настольного клиента Teams для пользователей, которые имеют доступ к Skype для бизнеса в Германии. | Миграция перемещает пользователей в Teams для совместной работы, вызова и чата. Развертывание настольного клиента Teams или обеспечение того, чтобы поддерживаемый браузер был доступен. | Клиенты Skype для бизнеса | Бездействие приведет к недоступности служб совместной работы Teams. |
| Анализ различий в функции лицензии между Microsoft Cloud Deutschland и Office 365 Services. | Службы Office 365 включают дополнительные функции и службы, недоступные в текущем Microsoft Cloud Deutschland. Во время передачи подписки пользователям будут доступны новые функции. | Все клиенты | - Анализ различных функций, предоставляемых лицензиями для Microsoft Cloud Deutschland и Office 365 Services. Начните с [описания службы платформы Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) <br><br> - Определите, следует ли сначала отключить какие-либо новые функции служб Office 365, чтобы ограничить влияние на пользователей или на управление изменением пользователей, и при необходимости изменить назначения лицензий пользователей. <br><br> Подготовка пользователей и сотрудников службы поддержки к новым службам и функциям, предоставляемым службами Office 365. |
| Создайте политики хранения [по всей организации,](https://docs.microsoft.com/microsoft-365/compliance/retention) чтобы защитить от непреднамеренного удаления контента во время миграции.  | - Чтобы во время миграции конечные пользователи не случайно удалили контент, клиенты могут включить политику хранения по всей организации. <br><br> - Хотя хранение не требуется, так как удержания, размещенные в любое время во время миграции, должны работать так, как ожидалось, политика хранения является механизмом обеспечения безопасности. В то же время политика хранения может использоваться не всеми клиентами, особенно теми, кто обеспокоен сохранением. | Клиенты Office | Применение политики хранения, как описано в ["Подробнее о политиках хранения и метки хранения".](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Сбои службы или клиентского программного обеспечения могут возникнуть, если это не будет сделано до этапа 4 из 9.  |
| Резервное копирование фермы служб Федерации Active [Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) для сценариев аварийного восстановления. | Клиенты должны надлежащим образом восстановить ферму AD FS, чтобы гарантировать восстановление доверчивых сторон к глобальным конечным точкам & Германии, не касаясь URI эмитента доменов. Корпорация Майкрософт рекомендует при необходимости использовать AD FS Rapid Restore для резервного копирования фермы и соответствующего восстановления. | Федерационные организации проверки подлинности | Обязательное действие. Бездействие приведет к влиянию службы во время миграции, если ферма AD FS клиента не справилась с управлением. Дополнительные сведения см. в [ADFS Migration steps] (https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |


## <a name="exchange-online"></a>Exchange Online

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Уведомлять внешних партнеров о предстоящем переходе на службы Office 365. | Конфигурации адресов доступности позволяют обмениваться бесплатными сведениями и сведениями о занятости в Office 365. | Клиенты Exchange Online, которые включили совместное использование календаря и адресного пространства доступности. | Обязательное действие.  Невыполнение этого может привести к сбою службы или клиента на более позднем этапе миграции клиентов. |
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


### <a name="for-hybrid-exchange"></a>Для гибридной Exchange

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Обновление до последней версии мастера гибридной конфигурации (HCW) перед миграцией. <br><br> Гибридные клиенты Microsoft Cloud Deutschland Exchange Online должны удалить предыдущие версии HCW, а затем установить и выполнить последнюю версию (17.0.5378.0 или выше) из [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | Последняя версия HCW содержит необходимые обновления для поддержки клиентов, которые переходят из Microsoft Cloud Deutschland в Office 365 Services. <br><br> Обновления включают изменения параметров локального сертификата для соединиттеля Отправка и соединителю получения. <br><br> Перед началом 5-го этапа 9 (миграция Exchange) клиенты должны повторно установить с помощью параметров Office 365 Germany. <br><br> ПРИМЕЧАНИЕ. После завершения миграции в службы Office 365 вы удалите и повторно установите HCW, на этот раз с помощью параметров Office 365 worldwide для завершения гибридной установки с помощью глобальной службы. | Клиенты Exchange Online, работающие с гибридным развертыванием | Обязательное действие. Невыполнение этого до этапа 5 из 9 (миграция Exchange) может привести к сбою службы или клиента. |
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

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Ограничить рабочий процесс SharePoint 2013, который используется во время миграции SharePoint Online. | Уменьшите рабочий процесс SharePoint 2013 и завершите рабочий процесс во время полета перед переходами. | Клиенты SharePoint Online | Бездействие может привести к путанице пользователей и вызовам службы поддержки. |
|||||

## <a name="mobile"></a>Для мобильных устройств

Если используется решение для управления сторонними мобильными устройствами (MDM):

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Определите, требуется ли перенастройка после миграции. | Решения MDM могут быть нацелены `outlook.de` на конечные точки. При переходе на Службы Office 365 профили клиентов должны обновляться до URL-адреса служб Office 365. `outlook.office365.com` | Клиенты Exchange Online и MDM | Клиенты могут продолжать работать, пока конечная точка доступна, но они не будут работать, если конечные точки Microsoft Cloud Deutschland больше не `outlook.de` доступны. |
|||||

## <a name="line-of-business-apps"></a>Приложения для бизнеса

Если вы используете сторонние приложения-службы или бизнес-приложения, интегрированные с Office 365: 

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Определите, требуется ли перенастройка после миграции. | Сторонние службы и приложения, которые интегрируются с Office 365, могут быть закодироваться, чтобы ожидать IP-адреса и URL-адреса Microsoft Cloud Deutschland. | Все клиенты | Обязательное действие. Бездействие может привести к сбоям службы или клиентского программного обеспечения. |
|||||

## <a name="azure"></a>Azure 

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Определите, какие службы Azure используются, и подготовка к будущей миграции из Германии в клиента служб Office 365, работая с партнерами. Следуйте шагам, описанным в [книге миграции Azure.](https://docs.microsoft.com/azure/germany/germany-migration-main) | Миграция ресурсов Azure является обязанностью клиента и требует ручных усилий после предписанных действий. Понимание того, какие службы используются в организации, является ключом к успешной миграции служб Azure. <br><br> Клиенты Office 365 Germany, у которых есть подписки Azure под тем же разделом удостоверений (организация), должны следовать предписанным Microsoft порядком, когда они могут приступить к миграции подписки и служб. | Клиенты Azure | - Клиенты могут иметь несколько подписок Azure, каждая из которых содержит инфраструктуру, службы и компоненты платформы. <br><br> - Администраторы должны определить подписок и заинтересованных лиц, чтобы обеспечить оперативную миграцию и проверку возможно в рамках этого события миграции. <br><br> Неудача успешного переноса этих подписок и компонентов Azure в установленные сроки повлияет на завершение перехода Office и Azure AD на службы Office 365 и может привести к потере данных.  <br><br> - Уведомление центра сообщений будет сигнализировать о том, с какой точки может начаться миграция под руководством клиента. |
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

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Для подписки на песочницу Dynamics 365 обязательно скачайте производственную среду экземпляра Dynamics SQL из подписки Dynamics 365 в Microsoft Cloud Deutschland. Последняя резервная копия должна быть восстановлена в песочнице до переноса песочницы. | Миграция Dynamics 365 требует от клиентов обновления среды песочницы с помощью последней производственной базы данных. | Клиенты Microsoft Dynamics | Команда FastTrack поможет клиентам выполнять сухие запуски для проверки обновления версии с 8.x до 9.1.x. |
|||||

## <a name="power-bi"></a>Power BI

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Удаление объектов из подписок Power BI, которые не будут перенесены из Power BI Microsoft Cloud Deutschland в службы Office 365. | Миграция служб Power BI потребует действий клиента для удаления определенных артефактов, таких как наборы данных и панели мониторинга. | Клиенты Power BI | Администраторам может потребоваться удалить следующие элементы из подписки: <br> - Real-Time наборы данных (например, наборы потоковой передачи или push-данных) <br> - Конфигурация и источник данных power BI локального шлюза данных |
|||||

## <a name="dns"></a>DNS

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Удалите MSOID, CName из DNS, который принадлежит клиенту, если он существует в любое время до переключеть Azure AD. TTL можно установить в течение 5 минут, чтобы изменение быстро вступает в силу. | Изменения зоны DNS, которые принадлежат клиенту | Клиенты служб Office | 
|||||

## <a name="federated-identity"></a>Федеративное удостоверение

| Step(s) | Описание | Область применения | Влияние |
|:-------|:-----|:-------|:-------|
| Добавьте идентификатор для одного входного знака (SSO) в существующую доверяющую сторону и отключим авто-обновления метаданных AD FS. | Перед началом миграции в доверение стороне AD FS необходимо добавить ID. Чтобы избежать случайного удаления идентификатора стороны, необходимо отключить автоматическое обновление для обновлений метаданных. <br><br> Запустите эту команду на сервере AD FS: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Федерационные организации проверки подлинности | Обязательное действие. Бездействие перед этапом 4 из 9 (SharePoint) приведет к влиянию службы во время миграции.  |
| Создание доверяющих сторон для глобальных конечных точек Azure AD. | Клиенты должны вручную создать доверение сторон (RPT) [к](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) глобальным конечным точкам. Это делается путем добавления нового RPT с помощью GUI, используя URL-адрес метаданных глобальной федерации, а затем используя правила утверждения [Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (в AD FS Help) для создания правил утверждения и импорта их в RPT. | Федерационные организации проверки подлинности | Обязательное действие. Бездействие приведет к воздействию службы во время миграции. |
|||||

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
