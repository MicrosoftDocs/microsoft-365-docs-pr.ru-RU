---
title: Поиск действий пользователей и администраторов в журнале аудита
f1.keywords:
- NOCSH
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
description: 'Журнал аудита является единым журналом аудита. Почему именно единый журнал аудита? Поскольку события из большинства служб, на которые подписана ваша организация, записываются в один журнал аудита, который можно искать. Это означает, что вы можете выполнять поиск действий пользователей и администраторов в следующих службах:'
ms.openlocfilehash: 95f5025e4831223c93251c7c22d1f43d44086d48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625099"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="17f44-106">Поиск действий пользователей и администраторов в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="17f44-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="17f44-107">Журнал аудита является единым журналом аудита.</span><span class="sxs-lookup"><span data-stu-id="17f44-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="17f44-108">Почему именно единый журнал аудита?</span><span class="sxs-lookup"><span data-stu-id="17f44-108">Why a unified audit log?</span></span> <span data-ttu-id="17f44-109">Так как события из большинства служб, на которые подписана организация, записываются в один журнал аудита, который можно искать.</span><span class="sxs-lookup"><span data-stu-id="17f44-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="17f44-110">Это означает, что вы можете выполнять поиск действий пользователей и администраторов в следующих службах:</span><span class="sxs-lookup"><span data-stu-id="17f44-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="17f44-111">SharePoint;</span><span class="sxs-lookup"><span data-stu-id="17f44-111">SharePoint</span></span>
- <span data-ttu-id="17f44-112">OneDrive;</span><span class="sxs-lookup"><span data-stu-id="17f44-112">OneDrive</span></span>
- <span data-ttu-id="17f44-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="17f44-113">Exchange</span></span>
- <span data-ttu-id="17f44-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="17f44-114">Azure Active Directory</span></span>
- <span data-ttu-id="17f44-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17f44-115">Microsoft Teams</span></span>
- <span data-ttu-id="17f44-116">Обнаружение электронных данных</span><span class="sxs-lookup"><span data-stu-id="17f44-116">eDiscovery</span></span>
- <span data-ttu-id="17f44-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="17f44-117">Power BI</span></span>
- <span data-ttu-id="17f44-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="17f44-118">Yammer</span></span>
- <span data-ttu-id="17f44-119">Sway</span><span class="sxs-lookup"><span data-stu-id="17f44-119">Sway</span></span>
- <span data-ttu-id="17f44-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="17f44-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="17f44-121">Настройка аудита</span><span class="sxs-lookup"><span data-stu-id="17f44-121">Set up auditing</span></span>
  
<span data-ttu-id="17f44-122">Прежде чем выполнять поиск в журнале аудита, необходимо выполнить несколько действий.</span><span class="sxs-lookup"><span data-stu-id="17f44-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="17f44-123">[Включение поиска в журнале аудита](turn-audit-log-search-on-or-off.md) для запуска записи событий, которые можно искать</span><span class="sxs-lookup"><span data-stu-id="17f44-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="17f44-124">[Включите аудит почтовых ящиков](enable-mailbox-auditing.md) , чтобы можно было искать события, связанные с почтовыми ящиками; Например, когда пользователь входит в свой почтовый ящик или удаляет элементы из папки "элементы с возможностью восстановления"</span><span class="sxs-lookup"><span data-stu-id="17f44-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="17f44-125">Поиск в журнале аудита</span><span class="sxs-lookup"><span data-stu-id="17f44-125">Search the audit log</span></span>
  
<span data-ttu-id="17f44-126">После включения аудита вы ищете сотни отдельных типов событий от нескольких служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="17f44-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="17f44-127">Поиск действий пользователей и администраторов [в журнале аудита](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="17f44-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="17f44-128">[Изучите подробные свойства](detailed-properties-in-the-office-365-audit-log.md) каждой записи аудита, включенной в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="17f44-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="17f44-129">[Поиск действий, связанных с обнаружением электронных](search-for-ediscovery-activities-in-the-audit-log.md) данных, выполняемых администраторами и диспетчерами соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="17f44-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
