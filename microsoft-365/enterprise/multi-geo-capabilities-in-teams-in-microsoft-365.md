---
title: Возможности multi-Geo в Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Узнайте, как Teams с Microsoft 365 Multi-Geo.
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453529"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="c419a-103">Возможности Multi-Geo в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c419a-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="c419a-104">Возможности Multi-Geo в Teams позволяют хранить Teams в покое в указанном географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="c419a-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="c419a-105">Данные чата состоят из сообщений чата, в том числе частных сообщений, сообщений каналов и изображений, используемых в чатах.</span><span class="sxs-lookup"><span data-stu-id="c419a-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="c419a-106">Teams для определения, где хранить данные, используется предпочтительное расположение данных (PDL) для пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="c419a-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="c419a-107">Если PDL не установлен или недействителен, данные хранятся в центральном расположении клиента.</span><span class="sxs-lookup"><span data-stu-id="c419a-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="c419a-108">Пользовательский чат</span><span class="sxs-lookup"><span data-stu-id="c419a-108">User chat</span></span>

<span data-ttu-id="c419a-109">Пользовательский чат включает индивидуальные, индивидуальные и частные сообщения о собраниях.</span><span class="sxs-lookup"><span data-stu-id="c419a-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="c419a-110">После создания нового пользователя Teams PDL пользователя и сохраняет все данные чата в этом географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="c419a-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="c419a-111">Для существующих пользователей, если администратор добавляет или изменяет PDL для пользователя, эти данные чата пользователя добавляются в очередь миграции, которая будет перемещена в указанное географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="c419a-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="c419a-112">Расположение хранилища для чата "один к одному" или "один к многим" основано на PDL человека, создавшего чат.</span><span class="sxs-lookup"><span data-stu-id="c419a-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="c419a-113">Если PDL этого пользователя будет изменен, чат будет перенесен в новое географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="c419a-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="c419a-114">Расположение хранилища для чата собраний основано на PDL организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="c419a-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="c419a-115">Чтобы найти текущее расположение данных Teams пользователя, подключите [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c419a-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="c419a-116">Сообщения канала</span><span class="sxs-lookup"><span data-stu-id="c419a-116">Channel messages</span></span>

<span data-ttu-id="c419a-117">Каждая Microsoft 365 группа имеет предпочтительное расположение данных (PDL), которое обозначает географическое расположение, в котором должны храниться соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="c419a-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="c419a-118">Teams использует PDL для группы, связанной с каждой командой, чтобы определить, где хранить данные обмена сообщениями каналов для этой группы.</span><span class="sxs-lookup"><span data-stu-id="c419a-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="c419a-119">Это включает частные каналы, а также чат, который происходит в собрании канала.</span><span class="sxs-lookup"><span data-stu-id="c419a-119">This includes private channels as well as chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="c419a-120">Когда пользователь создает новую команду, PDL этого пользователя определяет, какой PDL назначен Microsoft 365 группе.</span><span class="sxs-lookup"><span data-stu-id="c419a-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="c419a-121">PDL группы определяет, где хранятся данные этой группы.</span><span class="sxs-lookup"><span data-stu-id="c419a-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="c419a-122">Если PDL этого пользователя позже изменяется, PDL группы не изменяется.</span><span class="sxs-lookup"><span data-stu-id="c419a-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="c419a-123">Для существующих групп, если администратор добавляет или изменяет PDL для группы Microsoft 365, которая возвращает группу, данные о каналах обмена сообщениями этой группы добавляются в очередь миграции, которая будет перемещена в указанное географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="c419a-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="c419a-124">Изменение PDL группы Microsoft 365 очереди Teams данных для переноса в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="c419a-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="c419a-125">Однако это не переносит SharePoint или файлы, связанные с Группой автоматически.</span><span class="sxs-lookup"><span data-stu-id="c419a-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="c419a-126">Вы должны переместить сайт отдельно, следуя процедурам в [Move a SharePoint в другое географическое расположение.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)</span><span class="sxs-lookup"><span data-stu-id="c419a-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="c419a-127">Не забудьте сделать оба шага, чтобы избежать Teams и SharePoint данных для одной группы в разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="c419a-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="c419a-128">Чтобы найти текущее расположение данных группы, подключись к [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c419a-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="c419a-129">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="c419a-129">User Experience</span></span>

<span data-ttu-id="c419a-130">Teams Multi-Geo является бесшовным для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c419a-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="c419a-131">После изменения PDL пользователя или группы соответствующие данные будут стоять в очереди для миграции, и миграция будет происходить автоматически без каких-либо последствий для пользователя или Teams клиента, даже если они активны во время миграции.</span><span class="sxs-lookup"><span data-stu-id="c419a-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="c419a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c419a-132">See also</span></span>

[<span data-ttu-id="c419a-133">Конфигурация клиента Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="c419a-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="c419a-134">Администрирование среды с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="c419a-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="c419a-135">Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="c419a-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
