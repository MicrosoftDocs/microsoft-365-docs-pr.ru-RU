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
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a><span data-ttu-id="f147f-103">Back up data before switching Microsoft 365 for business plans</span><span class="sxs-lookup"><span data-stu-id="f147f-103">Back up data before switching Microsoft 365 for business plans</span></span>

<span data-ttu-id="f147f-104">Если пользователь перейдет на другую подписку, которая имеет меньше служб, связанных с данными, или пользователь покинет организацию, перед переходом на новую подписку можно скачать копию данных, хранимых в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f147f-104">If a user will be switched to another subscription that has fewer data-related services or a user leaves the organization, a copy of their data that's stored in Microsoft 365 can be downloaded before they are switched to the new subscription.</span></span>

<span data-ttu-id="f147f-105">Если вы перемещает пользователя в подписку, которая имеет те же или несколько служб, вам не нужно возвращать данные пользователей.</span><span class="sxs-lookup"><span data-stu-id="f147f-105">If you're moving a user to a subscription that has the same or more services, you don't need to back up user data.</span></span> <span data-ttu-id="f147f-106">См. [в журнале Move users to a different subscription.](./move-users-different-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="f147f-106">See [Move users to a different subscription](./move-users-different-subscription.md).</span></span>
  
## <a name="save-a-copy-of-outlook-information"></a><span data-ttu-id="f147f-107">Сохранение копии данных Outlook</span><span class="sxs-lookup"><span data-stu-id="f147f-107">Save a copy of Outlook information</span></span>

<span data-ttu-id="f147f-108">Если у пользователей есть Outlook, они могут экспортировать или резервное копирование электронной почты, контактов и календаря в [файл Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) перед переключение плана.</span><span class="sxs-lookup"><span data-stu-id="f147f-108">If users have Outlook, they can [export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) before their plan is switched.</span></span>
  
<span data-ttu-id="f147f-109">После завершения перехода на новый план пользователи могут импортировать электронную почту, контакты и календарь из [файла Outlook .pst.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)</span><span class="sxs-lookup"><span data-stu-id="f147f-109">After the switch to the new plan is finished, users can [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>
  
## <a name="save-files-stored-in-onedrive-for-business"></a><span data-ttu-id="f147f-110">Сохранение файлов, хранимых в OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f147f-110">Save files stored in OneDrive for Business</span></span>

<span data-ttu-id="f147f-111">Перед переходом на другую подписку пользователи могут загружать файлы и папки [из OneDrive](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) или SharePoint в другое расположение, например папку на жестком диске компьютера или файл в сети организации.</span><span class="sxs-lookup"><span data-stu-id="f147f-111">Before being switched to a different subscription, users can [download files and folders from OneDrive or SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) to a different location, such as a folder on their computer's hard drive, or a file share on the organization's network.</span></span>
  
## <a name="save-yammer-information"></a><span data-ttu-id="f147f-112">Сохранение сведений о Yammer</span><span class="sxs-lookup"><span data-stu-id="f147f-112">Save Yammer information</span></span>

<span data-ttu-id="f147f-113">Администраторы могут экспортировать все сообщения, заметки, файлы, темы, пользователей и группы в .zip файл.</span><span class="sxs-lookup"><span data-stu-id="f147f-113">Admins can export all messages, notes, files, topics, users, and groups to a .zip file.</span></span> <span data-ttu-id="f147f-114">Дополнительные сведения см. в [экспорте данных yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)</span><span class="sxs-lookup"><span data-stu-id="f147f-114">For more information, see [Export data from Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data).</span></span> <span data-ttu-id="f147f-115">Для этого разработчики могут использовать [API Yammer.](https://go.microsoft.com/fwlink/p/?linkid=842495)</span><span class="sxs-lookup"><span data-stu-id="f147f-115">Developers can use the [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) to do this, as well.</span></span>
  
## <a name="how-to-save-sharepoint-information"></a><span data-ttu-id="f147f-116">Как сохранить данные SharePoint</span><span class="sxs-lookup"><span data-stu-id="f147f-116">How to save SharePoint information</span></span>

<span data-ttu-id="f147f-117">Если пользователь перейдет из подписки с SharePoint Online на нее, плитка **SharePoint** больше не будет отображаться в меню Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f147f-117">If a user is switched from a subscription that has SharePoint Online to one that doesn't have it, the **SharePoint** tile will no longer appear in their Microsoft 365 menu.</span></span>
  
<span data-ttu-id="f147f-p103">Однако поскольку обе подписки относятся к одной и той же организации, у пользователя по-прежнему будет доступ к сайту группы SharePoint. Он сможет просматривать и обновлять записные книжки, документы, задачи и календари, переходя на сайт группы непосредственно по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f147f-p103">However, as long as the new subscription is within the same organization as the one they are switched from, users will still be able to access the SharePoint team site. They can view and update notebooks, documents, tasks, and calendars by using the direct URL to the team site.</span></span>
  
> [!TIP]
> <span data-ttu-id="f147f-120">Мы рекомендуем пользователям перейти на сайт группы до смены подписки и сохранить его URL-адрес как избранный элемент или закладку в браузере.</span><span class="sxs-lookup"><span data-stu-id="f147f-120">We recommend that users go to the team site before their subscription is switched and save the URL as a favorite or bookmark in their browser.</span></span>
  
<span data-ttu-id="f147f-121">По умолчанию URL-адрес веб-сайта группы имеет такой вид:</span><span class="sxs-lookup"><span data-stu-id="f147f-121">By default, the URL of the team website is in this form:</span></span>
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

<span data-ttu-id="f147f-122">где  _\<orgDomain\>_ URL-адрес организации.</span><span class="sxs-lookup"><span data-stu-id="f147f-122">where  _\<orgDomain\>_ is the organization's URL.</span></span>
  
<span data-ttu-id="f147f-123">Например, если домен организации  contoso.onmicrosoft.com, то URL-адрес для прямого доступа к сайту группы имеет вид `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.</span><span class="sxs-lookup"><span data-stu-id="f147f-123">For example, if the domain of the organization is contoso.onmicrosoft.com, then the direct URL to the team site would be `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.</span></span>
  
<span data-ttu-id="f147f-124">Разумеется, пользователи также могут в любое время скачать документы SharePoint Online с сайта группы SharePoint на локальный компьютер или в другое место.</span><span class="sxs-lookup"><span data-stu-id="f147f-124">Of course, users can also download SharePoint Online documents from the SharePoint team site to their local computer or to another location at any time.</span></span>
