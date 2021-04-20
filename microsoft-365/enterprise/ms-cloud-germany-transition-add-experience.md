---
title: Действия после миграции для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: Сводка. Действия после миграции после перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в службы Office 365 в новом немецком регионе центра обработки данных.
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899368"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Действия после миграции для миграции из Microsoft Cloud Deutschland

В следующих разделах предусматриваются действия после миграции для нескольких служб после перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в службы Office 365 в новом немецком регионе центра обработки данных.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Федерарная проверка подлинности Azure AD с помощью AD FS
**Применяется к:** Все клиенты, использующие федератированную проверку подлинности с помощью AD FS

| Step(s) | Description | Влияние |
|:-------|:-------|:-------|
| Удаление доверчивых партийных трастов из Microsoft Cloud Deutschland AD FS. | После завершения подключения к Azure AD организация полностью использует службы Office 365 и больше не подключена к Microsoft Cloud Deutschland. На этом этапе клиенту необходимо удалить доверение доверчивых сторон конечным точкам Microsoft Cloud Deutschland. Это можно сделать только в том случае, если ни одно из приложений клиента не указывает на конечные точки Microsoft Cloud Deutschland, когда Azure AD будет использовать в качестве поставщика удостоверений (IdP). | Федерационные организации проверки подлинности | Отсутствуют. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Утверждения группы
**Применяется к:** Конечные пользователи, запросы на утверждение группы Azure AD не были утверждены за последние 30 дней до миграции 

| Step(s) | Description | Влияние |
|:-------|:-------|:-------|
| Запросы на вступление в группу Azure AD в течение последних 30 дней до миграции необходимо будет снова запрашивать, если первоначальный запрос не был утвержден. | Клиенты конечных пользователей должны будут использовать панель Access для отправки запроса на повторное присоединение к группе Azure AD, если эти запросы не были утверждены за последние 30 дней до переноса. |  Как конечный пользователь: <ol><li>Перейдите к [панели Access.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Найдите группу Azure AD, для которой утверждение членства ожидалось в течение 30 дней до миграции.</li><li>Запрос на повторное вступление в группу Azure AD.</li></ol> Запросы на вступление в группу, активную менее чем за 30 дней до миграции, не могут быть утверждены, если они не будут снова запрашиваться после миграции. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Настраиваемые обновления DNS
**Применяется к:**  Все клиенты, управляющие своими зонами DNS

| Step(s) | Description | Влияние |
|:------|:-------|:-------|
| Обновление локальной службы DNS для конечных точек служб Office 365. | Записи DNS, управляемые клиентом, указывающие на Microsoft Cloud Deutschland, необходимо обновить, чтобы указать на конечные точки глобальных служб Office 365. | Невыполнение этого может привести к сбою службы или клиентов программного обеспечения. |
||||

## <a name="third-party-services"></a>Сторонние службы
**Применяется к:** Клиенты, использующие сторонние службы для конечных точек служб Office 365

| Step(s) | Description | Влияние |
|:-------|:-------|:-------|
| Обновление партнеров и сторонних служб для конечных точек служб Office 365. | <ul><li>Сторонние службы и партнеры, которые указывают на Office 365 в Германии, необходимо обновить, чтобы указать конечные точки служб Office 365. Пример. Перерегистрируйтесь в соответствии с вашими поставщиками и партнерами, если это доступно, версия приложения-галереи. </li><li>Указать все настраиваемые приложения, которые используют API Graph от `graph.microsoft.de` до `graph.microsoft.com` . Другие API с измененными конечными точками также должны быть обновлены, если они будут заемными. </li><li>Измените все непредназначимые корпоративные приложения, чтобы перенаправить их на конечные точки по всему миру. </li></ul>| Обязательное действие. Невыполнение этого может привести к сбою службы или клиентов программного обеспечения. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Применяется к**: Клиенты, использующие рабочий процесс SharePoint 2013

| Step(s) | Description | Влияние |
|:-------|:-------|:-------|
| Переопубликовка рабочего процесса SharePoint 2013. | В работе перед миграцией мы сократили число процессов SharePoint 2013. Теперь, когда миграция завершена, клиент может переопубликовать рабочий процесс. | Это необходимое действие. Невыполнение этого может привести к путанице пользователей и вызовам службы поддержки. |
| Доля элементов через Outlook | Совместное использование элементов в SharePoint Online и OneDrive для бизнеса через Outlook больше не работает после сокращения клиентов. |<ul><li>В SharePoint Online и OneDrive для бизнеса можно обмениваться элементами через Outlook. После нажатия кнопки Outlook создается совместное сообщение, которое будет перенажато в новое сообщение в Outlook Web App.</li><li>После сокращения клиента этот метод обмена не будет работать. Мы признаем, что это известная проблема. Однако, так как эта функция Outlook находится на пути амортизации, исправление проблемы не планируется до тех пор, пока не будет откат. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Применяется к**: Клиенты, использующие гибридную конфигурацию Exchange

| Step(s) | Description | Влияние |
|:-------|:-------|:-------|
| Повторное повторе мастера гибридной конфигурации (HCW) в отношении служб Office 365. | Существующая конфигурация HCW предназначена для поддержки Microsoft Cloud Deutschland. С завершением миграции служб Exchange мы отожмем локальное расположение от Microsoft Cloud Deutschland. |<ul><li>Обязательное действие. Невыполнение этого может привести к сбою службы или клиентов программного обеспечения. Перед началом миграции почтовых ящиков Exchange (с 5 или более днями уведомления) уведомляйте клиентов о том, что они должны остановить и удалить любые перемещения почтовых ящиков.  Если этого не делать, они будут видеть ошибки в запросах на перемещение. </li><li>После завершения миграции почтовых ящиков Exchange уведомите клиентов о том, что они могут возобновить перемещение бортовых и отсоедом. <br> Запуск **test-MigrationServerAvailabiilty**— это комдлет PowerShell во время переноса служб Exchange из Microsoft Cloud Deutschland в службы Office 365 может не работать. Однако после завершения миграции она будет работать правильно. </li><li>Если у клиентов после переноса почтовых ящиков могут быть проблемы с учетными данными или авторизацией, пользователи могут повторно входить в конечную точку миграции, используя панель управления `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange (ECP). </li></ul>|
