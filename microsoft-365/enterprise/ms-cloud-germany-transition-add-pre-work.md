---
title: Действия по предварительной миграции для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
description: Сводка. Предварительная работа при переходе из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.
ms.openlocfilehash: 08774cdfd831556c194b5175879f211efa250632
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362742"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Действия по предварительной миграции для миграции из Microsoft Cloud Deutschland

Используйте эти ссылки, чтобы добраться до этапов предварительной миграции, соответствующих организации.

Если вы используете

- **Office 365 Microsoft Cloud Deutschland**, сделайте [эти шаги](#general-tenant-migration-considerations).
- **Настраиваемые домены**, сделать [этот шаг](#dns-entries-for-custom-domains).
- **Office Приложения**, рассмотрим [этот шаг](#office-apps).
- **SharePoint Online,** [сделайте этот шаг](#sharepoint-online).
- **Exchange Online** **или Exchange Гибрид**, сделать [этот шаг](#exchange-online).
- **Skype для бизнеса Online,** сделайте [этот шаг](#skype-for-business-online).
- **Dynamics 365**, сделать [этот шаг](#dynamics-365).
- **Power BI**, сделать [этот шаг](#power-bi).
- **Службы федерации Active Directory** для azure AD Подключение, сделайте [эти действия.](#active-directory-federation-services-ad-fs)
- **Сторонние службы** или **бизнес-приложения,** интегрированные с Office 365, делают [этот шаг.](#line-of-business-apps)
- Решение для управления мобильными устройствами сторонних пользователей (MDM) должно [сделать этот шаг.](#mobile-device-management)
- **Службы Azure** с Office 365 подпиской, [сделайте этот шаг.](#microsoft-azure)

## <a name="general-tenant-migration-considerations"></a>Общие соображения миграции клиента

**Применяется к:** Все клиенты, Office 365 в экземпляре Microsoft Deutschland Cloud

Office 365 и идентификаторы пользователей сохраняются во время миграции. Вызовы служб Azure AD перенаправляются из Microsoft Cloud Deutschland в Office 365 глобальные службы и прозрачны для Office 365 служб.

- Общие запросы субъектов защиты данных (GDPR) выполняются с портала Администрирования Azure для будущих запросов. Все устаревшие или нестандартные диагностические данные, проживающие в Microsoft Cloud Deutschland, удаляются в течение или до 30 дней.

- Многофакторная проверка подлинности (MFA) с использованием Microsoft Authenticator в качестве пользователя ObjectID (GUID) в то время как клиент копируется в Office 365 службы. Запросы MFA будут выполняться, как и ожидалось, несмотря на такое поведение отображения.  Microsoft Authenticator учетные записи, активированные с помощью конечных точек Office 365 служб, будут отображать основное имя пользователя (UPN).  Учетные записи, добавленные с помощью конечных точек Microsoft Cloud Deutschland, будут отображать объектный объект пользователя, но будут работать как с конечными точками Microsoft Cloud Deutschland, так и Office 365 службами.

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Подготовка к оповещению пользователей о перезапуске и входе в клиенты после миграции.|Office клиентского лицензирования будет переход от Microsoft Cloud Deutschland к Office 365 служб миграции. Клиенты выбирают новую допустимую лицензию после регистрации в Office клиентов.|Продукты Office необходимо обновить лицензии от Office 365 служб. Если лицензии не обновляются, Office могут возникнуть ошибки проверки лицензии.|
|Обеспечение подключения к [сети для Office 365 url-адресов служб и IP-адресов.](https://aka.ms/o365urls)|Все клиенты и службы, используемые для доступа к Office 365, должны иметь доступ к конечным точкам Office 365 глобальных служб. <p> Если у вас или ваших партнеров по совместной работе есть правила брандмауэра, препятствующие доступу к URL-адресам и IP Office 365 указанным в [URL-адресах](https://aka.ms/o365urls) служб Office 365, необходимо изменить правила брандмауэра, чтобы разрешить доступ к конечным точкам Office 365 глобальной службы.|Сбои службы или клиентского программного обеспечения могут возникнуть, если это не будет сделано до этапа 4|
|Отмена пробных подписок.|Пробные подписки не будут перенесены и будут блокировать передачу платных подписок.|Пробные службы истекают и не функционируют, если к ним после отмены будут доступны пользователи.|
|Анализ различий в свойствах лицензий между Microsoft Cloud Deutschland и Office 365 Global Services.|Office 365 службы включают дополнительные функции и службы, недоступные в текущем Microsoft Cloud Deutschland. Во время передачи подписки пользователям будут доступны новые функции.|<ul><li>Анализ различных функций, предоставляемых лицензиями для Microsoft Cloud Deutschland и Office 365 Global Services. Начните с [описания Office 365 платформы.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)</li><li>Определите, следует ли сначала отключить какие-либо новые функции Office 365 служб, чтобы ограничить влияние на пользователей или на управление изменением пользователей, а также при необходимости изменить назначения лицензий пользователей.</li><li>Подготовка пользователей и сотрудников службы поддержки к новым службам и функциям, предоставляемым Office 365 службами.</li></ul>|
|Создайте политики хранения [по всей организации,](/microsoft-365/compliance/retention) чтобы защитить от непреднамеренного удаления контента во время миграции.|<ul><li>Чтобы содержимое не было случайно удалено конечными пользователями во время миграции, клиенты могут включить политику хранения по всей организации.</li><li>Хотя хранение не требуется, так как удержания, размещенные в любое время во время миграции, должны работать так, как ожидалось, политика хранения является механизмом обеспечения безопасности. В то же время политика хранения может использоваться не всеми клиентами, особенно теми, кто обеспокоен сохранением.</li></ul>|Применение политики хранения, как описано в ["Подробнее о политиках хранения и метки хранения".](/microsoft-365/compliance/retention-policies) Сбои службы или клиентского программного обеспечения могут возникнуть, если это не будет сделано до этапа 4 из 9.|


## <a name="dns-entries-for-custom-domains"></a>Записи DNS для пользовательских доменов

<!-- before phase 9 -->

**Применяется к**: Клиенты, задавшие настраиваемый _msoid_ CNAME в своем домене DNS или использующие домен для Exchange Online

Если настроено, _msoid_ CNAME затрагивает только клиентов, использующих Office desktop client (Приложения Microsoft 365, Office 365 профессиональный плюс, Office 2019, 2016, ...).

Если в одном или многих пространствах имен DNS, которые у вас есть, установленО DNS CNAME под названием _msoid,_ необходимо удалить CNAME не позднее конца 8-й фазы. Msoid CNAME  можно удалить в любое время до окончания этапа 8.

Чтобы убедиться, что в пространстве имен DNS установлен CNAME, выполните действия ниже _и замените_ contoso.com своим доменным именем:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Если командная строка возвращает запись DNS, удалите _msoid_ CNAME из домена.

> [!NOTE]
> Если вы используете настраиваемый домен для Exchange Online, необходимо иметь доступ к поставщику DNS-хостинга. Пожалуйста, убедитесь, что вы можете получить доступ и изменить параметры DNS, вы будете изменять записи DNS во время миграции.

## <a name="office-apps"></a>Office Приложения

**Применяется к**: Клиенты, использующие Office приложения, особенно Windows клиенты <br>
**При применении:** в любое время до начала этапа 9

Office 365, переехав в регион "Германия", требуют, чтобы все пользователи закрыли, вышли из Office 365 и вернулись для всех настольных приложений Office (Word, Excel, PowerPoint, Outlook и т.д.) и OneDrive для бизнеса клиента после того, как миграция клиента достигла этапа 9. Вход и вход позволяют службам Office получать новые маркеры проверки подлинности из глобальной службы Azure AD.

Это необходимо для всех клиентов. Чтобы обеспечить плавную миграцию, настоятельно рекомендуется заблаговременно и на ранней стадии информировать и инструктировать всех пострадавших пользователей об этом предстоящем действии.

Клиенты с управляемыми Windows клиенты могут подготовить Windows с помощью Office средства клиентской перереза [(OCCT).](https://github.com/microsoft/OCCT) OCCT предназначен для периодических Windows клиентов до тех пор, пока клиент не достиг этапа 9 миграции. По завершению 9-го этапа OCCT автоматически выполняет все необходимые изменения на компьютере без взаимодействия с пользователем.

OCCT можно развернуть на Windows клиентах в любое время до 9-го этапа. Если OCCT поддерживает процесс миграции, рекомендуется как можно скорее начать развертывание, чтобы оборудовать максимальное число клиентов.

## <a name="active-directory-federation-services-ad-fs"></a>Службы федерации Active Directory (AD FS)

**Применяется к**: Клиенты, использующие AD FS в помещениях для проверки подлинности пользователей, подключающихся к Microsoft Office 365<br>
**При применении:** в любое время до начала фазы 2

Чтение и применение [этапов миграции ADFS](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**Применяется к**: Клиенты, использующие SharePoint 2013 на локальной основе<br>
**При применении**: в любое время до начала этапа 4

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Ограничь SharePoint 2013 г., используйте во время миграции SharePoint Online.|Сокращение SharePoint 2013 г. и завершение рабочего процесса во время полета перед переходами.|Бездействие может привести к путанице пользователей и вызовам службы поддержки.|


## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Применяется к**: Exchange Online клиентам<br>
**При применении:** в любое время до окончания 9-го этапа

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Уведомлять внешних партнеров о предстоящем переходе Office 365 служб.|Клиенты должны уведомить своих партнеров, с которыми они включили общий доступ к календарю и конфигурации адресов доступности (разрешить совместное использование бесплатных и загруженных сведений с Office 365). Конфигурация доступности должна перейти к использованию конечных точек Office 365 во всем мире после Exchange Online миграции. [](/microsoft-365/enterprise/urls-and-ip-address-ranges)|Невыполнение этого может привести к сбою службы или клиента на более позднем этапе миграции клиентов.|
|Уведомлять пользователей о необходимых изменениях клиента IMAP4/POP3/SMTP.|Пользователи, подключенные к конечным точкам Microsoft Cloud Deutschland для клиентских протоколов IMAP4, POP3, SMTP, [](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes)должны вручную обновлять свои клиентские устройства, чтобы перейти на имена Exchange Online серверов.|Передай эту зависимость пользователям этих протоколов и убедитесь, что они либо переключаются на Outlook, либо Outlook в Интернете во время этой миграции. Если клиентские конечные точки не будут обновлены, при миграции почтовых ящиков пользователей будут сбои в работе с microsoft Cloud Deutschland.|


### <a name="exchange-online-hybrid-customers"></a>Exchange Online Гибридные клиенты

**Применяется к:** Все клиенты, использующие Exchange гибридную конфигурацию с Exchange локального сервера<br>
**При применении**: в любое время до начала фазы 5

Enterprise клиенты с гибридным развертыванием Exchange Online и локальной Exchange Server запускают мастер гибридной конфигурации (HCW) и AAD Подключение для поддержания и создания гибридной установки.
Exchange Online Гибридные **администраторы должны выполнить мастер гибридной конфигурации (HCW) несколько раз** в рамках этого перехода.
При переходе из Microsoft Cloud Deutschland в регион Office 365 Германии администратор должен повторно запустить последнюю сборку HCW в режиме "Office 365 Германия" до начала миграции Exchange (фаза 5). Затем снова запустите HCW в режиме "Office 365 Worldwide" после завершения фазы 5, чтобы завершить локальное развертывание с Office 365 параметров региона Германии. Запуск HCW не должен выполняться во время фазы 5, важно запустить HCW не до завершения фазы 5.
Атрибуты Directory синхронизируются Office 365 Azure AD с локальной развертыванием через AAD Подключение.

<br>

**

|Step(s)|Описание|Влияние|
|---|---|---|
|Повторное запуск HCW с Office 365 параметров Германии <p> _Вы можете начать это действие сразу после получения уведомления центра сообщений о начале миграции Office 365 клиента (этап 1)._|При отсечении и повторном запуске HCW (17.0.5378.0 или выше) до этапа 5 будет обеспечиваться готовность локальной конфигурации к отправке и приему почты как с пользователями Microsoft Cloud Deutschland, так и с пользователями, которые мигрируют в Office 365 Регион <https://aka.ms/hybridwizard> Германии. <p> В HCW, для списка ниже **Моя Office 365** организация находится , выберите Office 365 **Германии.**|Невыполнение этой задачи до начала фазы 5 [Exchange миграции] может привести к NDRs для почтовых отправлений, которые будут отправлены между локальной Exchange и Office 365.|
|Сохранение параметров общих почтовых ящиков|Некоторые гибридные клиенты превратили облачные почтовые ящики пользователей в "общие" почтовые ящики с Exchange Online командами. Эта конфигурация облачного почтового ящика записана в почтовый ящик и локальный каталог Exchange Online, однако она не синхронизируется с Active Directory клиента через AAD Подключение. Результатом этого является несоответствие между представлением Active Directory значений УдаленногоRecipientType почтового ящика и RemoteDisplayType и тем, что в Exchange Online определяет почтовый ящик как общий. <p> Клиент несет ответственность за то, чтобы все общие почтовые ящики были надлежащим образом обуярены с помощью `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` , или `Set-RemoteMailbox -Shared` . См. эту ссылку для преобразования почтового ящика пользователя [в гибридной среде.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox)|Невыполнеть эту задачу до этапа 5 [Exchange Online миграции] может привести к NDRs для общих почтовых ящиков, которые преобразуются в нелицензируемые почтовые ящики и потеря общего доступа для затронутых почтовых ящиков. [Общие почтовые](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) ящики неожиданно преобразуются в почтовые ящики пользователей после того, как синхронизация каталогов выполняется в гибридном развертывании Exchange описывает последствия непредназначения этого решения до завершения Exchange Online миграции.|


## <a name="skype-for-business-online"></a>Skype для Бизнеса Онлайн

<!-- before phase 7 -->

**Применяется к** клиентам : Skype для бизнеса в Интернете<br>
**При применении**: в любое время до начала фазы 7

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Развертывание Teams для пользователей, которые Skype для бизнеса в Германии.|Миграция Skype для бизнеса пользователей Microsoft Teams для совместной работы, звонков и чата. Либо разместим Microsoft Teams настольного клиента или убедитесь, что поддерживаемый браузер доступен.|Бездействие приведет к недоступности Microsoft Teams совместной работы.|
|Обзор и подготовка к изменениям DNS, связанных с миграцией.|Клиентская зона DNS изменяется для Skype для бизнеса Online.|<ul><li>Чтобы ускорить обновление записей DNS, рекомендуем обновить время до 5 минут для записей DNS любого домена, которые принадлежат клиенту. Однако управляемый Microsoft переключение, связанный с этим изменением DNS, может происходить в любое время в течение предоставленного 24-часового окна изменения.</li><li>В будущем возможны сбои в работе службы. Пользователи не смогут войти в Skype для бизнеса и будут перенаправлены на перенесенные Teams в Office 365 служб.</li></ul>|
|Подготовка подготовки конечных пользователей и администрирования и готовность к переходу на Microsoft Teams.|Будьте успешны при переходе с Skype на Teams, планируя взаимодействие с пользователями и готовность.|<ul><li>Клиенты должны знать о новых службах и о том, как использовать их после перехода на Office 365 службы.</li><li>После внесения изменений DNS как для доменов тщеславия клиентов, так и для исходного домена пользователи будут Skype для бизнеса и увидят, что теперь они перенесены в Teams. Это также загрузит настольный клиент для Teams в фоновом режиме.</li></ul>|


## <a name="mobile-device-management"></a>Управление мобильными устройствами

<!-- before phase 5 -->
**Применяется к:** Клиенты, использующие решение для управления сторонними мобильными устройствами (MDM).<br>
**При применении:** в любое время до начала фазы 5

<br>

****

|Step(s)|Описание|Сфера применения|Влияние|
|---|---|---|---|
|Подготовка обучения пользователей и администрирования об удалении и повторном добавлении учетной записи в Microsoft Outlook для iOS и Android.|Microsoft Outlook для учетных записей iOS и Android, настроенных с почтовыми ящиками в Microsoft Cloud Deutschland, возможно, придется удалить и снова добавить в Outlook, чтобы правильно синхронизировать новую конфигурацию Office 365 служб.|Microsoft Outlook для пользователей iOS и Android|Outlook почтовые ящики, настроенные ранее для Microsoft Cloud Deutschland, могут не выбирать новую конфигурацию служб Office 365, что приводит к ошибкам и ухудшению производительности других пользовательских интерфейсов. ИТ-администраторам рекомендуется предоставлять документацию, которая проактивно предписывает пользователям удалять и повторно добавлять свои учетные записи в Microsoft Outlook для iOS и Android, если проблемы с входом или синхронизацией почты возникают после миграции.|
|Определите, требуется ли перенастройка после миграции.|Решения для управления мобильными устройствами (MDM) могут быть нацелены `outlook.de` на конечные точки. При этом переходе Office 365 Службы профили клиентов должны обновляться до URL Office 365 служб, `outlook.office365.com` .|Exchange Online и MDM-клиенты|Клиенты могут продолжать работать, пока конечная точка доступна, но они не будут работать, если конечные точки Microsoft Cloud Deutschland больше не `outlook.de` доступны.|


## <a name="line-of-business-apps"></a>Приложения для бизнеса

**Применяется к:** Клиенты, использующие приложения для бизнеса (LOB) с конечными точками, предоставляемыми Microsoft Cloud Deutschland<br>
**При применении:** после завершения этапа 2 и до окончания 9-го этапа

Если вы используете сторонние приложения службы или бизнес-приложения, интегрированные с Office 365, необходимо устранить зависимости от конечных точек, предоставляемых экземпляром Microsoft Cloud Deutschland. Например, если к приложениям LOB подключаются приложения, необходимо `https://graph.microsoft.de/` изменить конечную точку на `https://graph.microsoft.com/` . Конечные точки глобальной Microsoft Office 365 становятся доступными для клиента после 2-го этапа.

Во время миграции, пока организация находится между 2-й и 9-й фазами, в организацию нельзя добавлять сторонние многоявостные приложения (MTA). После завершения 9-й фазы миграции можно возобновить добавление или согласие в приложения MTA для вашей организации.


| Step(s) | Описание | Влияние |
|:-------|:-------|:-------|
| Определите, требуется ли перенастройка после миграции. | Сторонние службы и приложения, которые интегрируются с Office 365, могут быть закодироваться, чтобы ожидать IP-адреса и URL-адреса Microsoft Cloud Deutschland. | Обязательное действие. Бездействие может привести к сбоям службы или клиентского программного обеспечения. |


|Step(s)|Описание|Влияние|
|---|---|---|
|Определите, требуется ли перенастройка после миграции.|Сторонние службы и приложения, которые интегрируются с Office 365, могут быть закодироваться, чтобы ожидать IP-адреса и URL-адреса Microsoft Cloud Deutschland.|Обязательное действие. Бездействие может привести к сбоям службы или клиентского программного обеспечения.|


## <a name="dynamics-365"></a>Dynamics 365

**Применяется к**: Клиенты, использующие Microsoft Dynamics 365

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Для подписки на песочницу Dynamics 365 обязательно скачайте производственную среду экземпляра Dynamics SQL из подписки Dynamics 365 в Microsoft Cloud Deutschland. Последняя резервная копия должна быть восстановлена в песочнице до переноса песочницы.|Миграция Dynamics 365 требует от клиентов обновления среды песочницы с помощью последней производственной базы данных.|Команда FastTrack поможет клиентам выполнять сухие запуски для проверки обновления версии с 8.x до 9.1.x.|


## <a name="power-bi"></a>Power BI

**Применяется к**: Клиенты, использующие Power BI

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Удаление объектов из Power BI, которые не будут перенесены из Power BI Microsoft Cloud Deutschland в Office 365 службы.|Миграция Power BI служб потребует действий клиента для удаления определенных артефактов, таких как наборы данных и панели мониторинга.|Администраторам может потребоваться удалить следующие элементы из подписки: <ul><li>Real-Time данных (например, наборы потоковой передачи или push-данных)</li><li>Power BI локальной конфигурации шлюза данных и источника данных </li></ul>|


## <a name="microsoft-azure"></a>Microsoft Azure

Если в экземпляре Microsoft Cloud Deutschland используется один и тот же раздел Azure Active Directory удостоверений для Office 365 и Microsoft Azure, убедитесь, что вы готовите к миграции служб Microsoft Azure клиентов.

> [!NOTE]
> Миграция служб Microsoft Azure не может начаться до того, как Office 365 клиент достиг этапа миграции 9 и должен быть завершен до начала 10-го этапа миграции.

Клиенты, Office 365 ресурсы Azure (например, сетевые, вычислительные и хранилища) будут выполнять перенос ресурсов в экземпляр Office 365 служб. Эта миграция является обязанностью клиента. Сообщения Центра сообщений будут сигнализировать о начале. Миграция должна быть завершена до завершения работы организации Azure AD в Office 365 служб. Для миграций Azure см. в книге "Руководство по миграции Azure", обзор руководства по миграции [для Azure Germany.](/azure/germany/germany-migration-main)

<br>

****

|Step(s)|Описание|Влияние|
|---|---|---|
|Определите, какие службы Azure используются, и подготовка к будущей миграции из Германии в клиент Office 365 служб, работая с партнерами. Следуйте шагам, описанным в [книге миграции Azure.](/azure/germany/germany-migration-main)|<ul><li>Миграция ресурсов Azure является обязанностью клиента и требует ручных усилий после предписанных действий. Понимание того, какие службы используются в организации, является ключом к успешной миграции служб Azure.</li><li>Office 365 Клиенты Из Германии, подписавшиеСя на Azure под тем же разделом удостоверений (организация), должны выполнять предписанный Microsoft порядок, когда они могут приступить к миграции подписок и служб.</li></ul>|<ul><li>Клиенты могут иметь несколько подписок Azure, каждая из которых содержит инфраструктуру, службы и компоненты платформы.</li><li>Администраторы должны определить подписок и заинтересованных лиц, чтобы обеспечить оперативную миграцию и проверку возможно в рамках этого события миграции.</li><li>Неудача успешного переноса этих подписок и компонентов Azure в установленные сроки повлияет на завершение перехода Office Azure AD на Office 365 службы и может привести к потере данных.</li><li>Уведомление центра сообщений будет сигнализировать о том, с какой точки может начаться миграция под руководством клиента.</li></ul>|


<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services.

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:**

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components.
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>Дополнительная информация

Начало работы:

- [Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных](ms-cloud-germany-transition.md)
- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Сведения о программе миграции Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here)
