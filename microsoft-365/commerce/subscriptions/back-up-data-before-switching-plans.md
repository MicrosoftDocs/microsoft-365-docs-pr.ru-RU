---
title: Back up data before changing plans
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Резервное копирование Outlook, OneDrive, Yammer и SharePoint перед изменением Microsoft 365 планов.
ms.date: 03/17/2021
ms.openlocfilehash: cdbeb7267105742082358dcd985e8fd1052a5679
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107428"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Back up data before switching Microsoft 365 for business plans

Если пользователь будет переключаться на другую подписку, которая имеет меньше служб, связанных с данными, или пользователь покидает организацию, копию данных, хранимые в Microsoft 365, можно скачать до перехода на новую подписку.

Если вы перемещает пользователя в подписку, которая имеет те же или несколько служб, вам не нужно возвращать данные пользователей. См. [в журнале Move users to a different subscription.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Сохранение копии Outlook

Если у пользователей Outlook, они могут экспортировать или резервное копирование электронной почты, контактов и календаря в [файл Outlook PST](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) перед переключение плана.
  
После завершения перехода на новый план пользователи могут импортировать электронную почту, контакты и календарь из [файла Outlook PST.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Сохранение файлов, хранимых в OneDrive для бизнеса

Перед переходом на другую подписку пользователи могут загружать файлы и папки из [OneDrive или SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) в другое расположение, например папку на жестком диске компьютера или файл в сети организации.
  
## <a name="save-yammer-information"></a>Сохранение Yammer

Администраторы могут экспортировать все сообщения, заметки, файлы, темы, пользователей и группы в .zip файл. Дополнительные сведения см. в [Yammer корпоративный.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) Разработчики также [могут использовать Yammer API.](https://go.microsoft.com/fwlink/p/?linkid=842495)
  
## <a name="how-to-save-sharepoint-information"></a>Как сохранить данные SharePoint

Если пользователь переключается с подписки, которая имеет SharePoint Online, на нее, плитка SharePoint больше не будет отображаться в Microsoft 365 меню. 
  
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