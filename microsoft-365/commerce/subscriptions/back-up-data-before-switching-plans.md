---
title: Резервное копирование данных перед изменением планов
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Резервное копирование содержимого Outlook, OneDrive, Yammer и SharePoint перед изменением планов Microsoft 365.
ms.openlocfilehash: 9acc97f65bb5b471cb992d7f01cd299192b74a52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818535"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Резервное копирование данных перед переключением Microsoft 365 для бизнес-планов

Если пользователь переключается на другую подписку с меньшим количеством служб, связанных с данными, или пользователь оставляет организацию, копия данных, сохраненных в Microsoft 365, может быть загружена перед переключением на новую подписку.
  
## <a name="save-a-copy-of-outlook-information"></a>Сохранение копии данных Outlook

Если у пользователей есть Outlook, они могут [экспортировать или архивировать сообщения электронной почты, контакты и календарь в PST-файл Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) перед переключением плана.
  
По завершении перехода к новому плану пользователи могут [импортировать электронную почту, контакты и календарь из PST-файла Outlook](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Сохранение файлов, хранящихся в OneDrive для бизнеса

Перед переключением на другую подписку пользователи могут [загружать файлы и папки из OneDrive или SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) в другое расположение, например папку на жестком диске компьютера или общую папку в сети Организации.
  
## <a name="save-yammer-information"></a>Сохранение сведений Yammer

Администраторы могут экспортировать в ZIP-файл все сообщения, заметки, файлы, темы, пользователей и группы. Дополнительные сведения содержатся в статье [Export Data из Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Кроме того, разработчики могут использовать [API Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) .
  
## <a name="how-to-save-sharepoint-information"></a>Как сохранить данные SharePoint

Если пользователь переключается из подписки с SharePoint Online на ту, у которой она нет, плитка **SharePoint** больше не будет отображаться в меню Microsoft 365.
  
Однако поскольку обе подписки относятся к одной и той же организации, у пользователя по-прежнему будет доступ к сайту группы SharePoint. Он сможет просматривать и обновлять записные книжки, документы, задачи и календари, переходя на сайт группы непосредственно по URL-адресу.
  
> [!TIP]
> Мы рекомендуем пользователям перейти на сайт группы до смены подписки и сохранить его URL-адрес как избранный элемент или закладку в браузере.
  
По умолчанию URL-адрес веб-сайта группы имеет такой вид:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

где _\<orgDomain\>_ — это URL-адрес Организации.
  
Например, если домен организации  contoso.onmicrosoft.com, то URL-адрес для прямого доступа к сайту группы имеет вид https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Разумеется, пользователи также могут в любое время скачать документы SharePoint Online с сайта группы SharePoint на локальный компьютер или в другое место.