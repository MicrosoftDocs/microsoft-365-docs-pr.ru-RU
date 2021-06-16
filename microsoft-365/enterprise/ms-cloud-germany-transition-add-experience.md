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
description: Сводка. Действия после миграции после перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930419"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Действия после миграции для миграции из Microsoft Cloud Deutschland

В следующих разделах предусматриваются действия после миграции для нескольких служб после перехода из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.

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

| Step(s) | Описание | Влияние |
|:-------|:-------|:-------|
| Удаление доверчивых партийных трастов из Microsoft Cloud Deutschland AD FS. | После завершения подключения к Azure AD организация полностью использует Office 365 и больше не подключена к Microsoft Cloud Deutschland. На этом этапе клиенту необходимо удалить доверение доверчивых сторон конечным точкам Microsoft Cloud Deutschland. Это можно сделать только в том случае, если ни одно из приложений клиента не указывает на конечные точки Microsoft Cloud Deutschland, когда Azure AD будет использовать в качестве поставщика удостоверений (IdP). | Федерационные организации проверки подлинности | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Утверждения группы
**Применяется к:** Конечные пользователи, запросы на утверждение группы Azure AD не были утверждены за последние 30 дней до миграции 

| Step(s) | Описание | Влияние |
|:-------|:-------|:-------|
| Запросы на вступление в группу Azure AD в течение последних 30 дней до миграции необходимо будет снова запрашивать, если первоначальный запрос не был утвержден. | Клиенты конечных пользователей должны будут использовать панель Access для отправки запроса на повторное присоединение к группе Azure AD, если эти запросы не были утверждены за последние 30 дней до переноса. |  Как конечный пользователь: <ol><li>Перейдите к [панели Access.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Найдите группу Azure AD, для которой утверждение членства ожидалось в течение 30 дней до миграции.</li><li>Запрос на повторное вступление в группу Azure AD.</li></ol> Запросы на вступление в группу, активную менее чем за 30 дней до миграции, не могут быть утверждены, если они не будут снова запрашиваться после миграции. |
||||

## <a name="custom-dns-updates"></a>Настраиваемые обновления DNS
**Применяется к:**  Все клиенты, управляющие своими зонами DNS

| Step(s) | Описание | Влияние |
|:------|:-------|:-------|
| Обновление локальной службЫ DNS для конечных точек Office 365 служб. | Записи DNS с управляемым клиентом, указывающие на Microsoft Cloud Deutschland, должны быть обновлены, чтобы указать на конечные точки Office 365 глобальных служб. Обратитесь к [доменам в центре администрирования Microsoft 365](https://admin.microsoft.com/Adminportal/Home#/Domains) и применяйте изменения в конфигурации DNS. | Невыполнение этого может привести к сбою службы или клиентов программного обеспечения. |
||||

## <a name="third-party-services"></a>Сторонние службы
**Применяется к:** Клиенты, использующие сторонние службы для конечных точек Office 365 служб

| Step(s) | Описание | Влияние |
|:-------|:-------|:-------|
| Обновление партнеров и сторонних служб для конечных точек Office 365 служб. | <ul><li>Сторонние службы и партнеры, которые указывают на Office 365 Германии, должны быть обновлены, чтобы указать на конечные точки Office 365 служб. Пример. Перерегистрируйтесь в соответствии с вашими поставщиками и партнерами, если это доступно, версия приложения-галереи. </li><li>Указать все настраиваемые приложения, Graph API `graph.microsoft.de` от до `graph.microsoft.com` . Другие API с измененными конечными точками также должны быть обновлены, если они будут заемными. </li><li>Измените все непредназначимые корпоративные приложения, чтобы перенаправить их на конечные точки по всему миру. </li></ul>| Обязательное действие. Невыполнение этого может привести к сбою службы или клиентов программного обеспечения. |
||||