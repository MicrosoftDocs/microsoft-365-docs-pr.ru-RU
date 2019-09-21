---
title: Поиск действий пользователей и администраторов в журнале аудита в Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'Журнал аудита Office 365 является единым журналом аудита. Зачем нужен единый журнал аудита? Поскольку события из большинства служб Office 365, на которые вы подписаны, записываются в один журнал аудита, который можно найти. Это означает, что вы можете выполнять поиск действий пользователей и администраторов в следующих службах:'
ms.openlocfilehash: 1d3f45d24a8d1a83c20f5d36b12ced761e00f936
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090748"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="daa81-106">Поиск действий пользователей и администраторов в журнале аудита в Office 365</span><span class="sxs-lookup"><span data-stu-id="daa81-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="daa81-107">Журнал аудита Office 365 является единым журналом аудита.</span><span class="sxs-lookup"><span data-stu-id="daa81-107">The Office 365 audit log is a unified audit log.</span></span> <span data-ttu-id="daa81-108">Зачем нужен единый журнал аудита?</span><span class="sxs-lookup"><span data-stu-id="daa81-108">Why a unified audit log?</span></span> <span data-ttu-id="daa81-109">Поскольку события из большинства служб Office 365, на которые вы подписаны, записываются в один журнал аудита, который можно найти.</span><span class="sxs-lookup"><span data-stu-id="daa81-109">Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="daa81-110">Это означает, что вы можете выполнять поиск действий пользователей и администраторов в следующих службах:</span><span class="sxs-lookup"><span data-stu-id="daa81-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="daa81-111">SharePoint;</span><span class="sxs-lookup"><span data-stu-id="daa81-111">SharePoint</span></span>
- <span data-ttu-id="daa81-112">OneDrive;</span><span class="sxs-lookup"><span data-stu-id="daa81-112">OneDrive</span></span>
- <span data-ttu-id="daa81-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="daa81-113">Exchange</span></span>
- <span data-ttu-id="daa81-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="daa81-114">Azure Active Directory</span></span>
- <span data-ttu-id="daa81-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daa81-115">Microsoft Teams</span></span>
- <span data-ttu-id="daa81-116">Обнаружение электронных данных (eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="daa81-116">eDiscovery</span></span>
- <span data-ttu-id="daa81-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="daa81-117">Power BI</span></span>
- <span data-ttu-id="daa81-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="daa81-118">Yammer</span></span>
- <span data-ttu-id="daa81-119">Sway</span><span class="sxs-lookup"><span data-stu-id="daa81-119">Sway</span></span>
- <span data-ttu-id="daa81-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="daa81-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="daa81-121">Настройка аудита</span><span class="sxs-lookup"><span data-stu-id="daa81-121">Set up auditing</span></span>
  
<span data-ttu-id="daa81-122">Прежде чем выполнять поиск в журнале аудита Office 365, необходимо выполнить несколько действий.</span><span class="sxs-lookup"><span data-stu-id="daa81-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="daa81-123">[Включение поиска в журнале аудита](turn-audit-log-search-on-or-off.md) для запуска записи событий, которые можно искать</span><span class="sxs-lookup"><span data-stu-id="daa81-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="daa81-124">[Включите аудит почтовых ящиков](enable-mailbox-auditing.md) , чтобы можно было искать события, связанные с почтовыми ящиками; Например, когда пользователь входит в свой почтовый ящик или удаляет элементы из папки "элементы с возможностью восстановления"</span><span class="sxs-lookup"><span data-stu-id="daa81-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="daa81-125">Поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="daa81-125">Search the audit log</span></span>
  
<span data-ttu-id="daa81-126">После включения аудита вы ищете сотни отдельных типов событий из нескольких служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="daa81-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="daa81-127">Поиск действий пользователей и администраторов [в журнале аудита](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="daa81-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="daa81-128">[Изучите подробные свойства](detailed-properties-in-the-office-365-audit-log.md) каждой записи аудита, включенной в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="daa81-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="daa81-129">[Поиск действий, связанных с обнаружением электронных](search-for-ediscovery-activities-in-the-audit-log.md) данных, выполняемых администраторами и диспетчерами соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="daa81-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
