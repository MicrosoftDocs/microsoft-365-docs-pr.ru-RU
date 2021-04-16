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
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Резервное копирование Outlook, контент OneDrive, Yammer и SharePoint перед изменением планов Microsoft 365.
ms.openlocfilehash: ecfd17d779cbb39ff786b192f72621bc94677776
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860527"
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

Администраторы могут экспортировать все сообщения, заметки, файлы, темы, пользователей и группы в файл .zip. Дополнительные сведения см. в [экспорте данных yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) Для этого разработчики могут использовать [API Yammer.](https://go.microsoft.com/fwlink/p/?linkid=842495)
  
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