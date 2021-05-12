---
title: Back up data before changing plans
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Резервное копирование Outlook, контент OneDrive, Yammer и SharePoint перед изменением планов Microsoft 365.
ms.date: 03/17/2021
ms.openlocfilehash: 86953f3235d8725ecdd6b5294611c0e5a378b17d
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333354"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Back up data before switching Microsoft 365 for business plans

Если пользователь перейдет на другую подписку, которая имеет меньше служб, связанных с данными, или пользователь покинет организацию, перед переходом на новую подписку можно скачать копию данных, хранимых в Microsoft 365.

Если вы перемещает пользователя в подписку, которая имеет те же или несколько служб, вам не нужно возвращать данные пользователей. См. [в журнале Move users to a different subscription.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Сохранение копии данных Outlook

Если у пользователей есть Outlook, они могут экспортировать или резервное копирование электронной почты, контактов и календаря в [файл Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) перед переключение плана.
  
После завершения перехода на новый план пользователи могут импортировать электронную почту, контакты и календарь из [файла Outlook .pst.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Сохранение файлов, хранимых в OneDrive для бизнеса

Перед переходом на другую подписку пользователи могут загружать файлы и папки [из OneDrive](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) или SharePoint в другое расположение, например папку на жестком диске компьютера или файл в сети организации.
  
## <a name="save-yammer-information"></a>Сохранение сведений о Yammer

Администраторы могут экспортировать все сообщения, заметки, файлы, темы, пользователей и группы в .zip файл. Дополнительные сведения см. в [экспорте данных yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) Для этого разработчики могут использовать [API Yammer.](https://go.microsoft.com/fwlink/p/?linkid=842495)
  
## <a name="how-to-save-sharepoint-information"></a>Как сохранить данные SharePoint

Если пользователь перейдет из подписки с SharePoint Online на нее, плитка **SharePoint** больше не будет отображаться в меню Microsoft 365.
  
Однако поскольку обе подписки относятся к одной и той же организации, у пользователя по-прежнему будет доступ к сайту группы SharePoint. Он сможет просматривать и обновлять записные книжки, документы, задачи и календари, переходя на сайт группы непосредственно по URL-адресу.
  
> [!TIP]
> Мы рекомендуем пользователям перейти на сайт группы до смены подписки и сохранить его URL-адрес как избранный элемент или закладку в браузере.
  
По умолчанию URL-адрес веб-сайта группы имеет такой вид:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

где  _\<orgDomain\>_ URL-адрес организации.
  
Например, если домен организации  contoso.onmicrosoft.com, то URL-адрес для прямого доступа к сайту группы имеет вид `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.
  
Разумеется, пользователи также могут в любое время скачать документы SharePoint Online с сайта группы SharePoint на локальный компьютер или в другое место.
