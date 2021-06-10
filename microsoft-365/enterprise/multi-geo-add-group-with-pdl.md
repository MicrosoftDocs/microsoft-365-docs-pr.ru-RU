---
title: Создание группы Microsoft 365 с определенным предпочтительным расположением данных
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Узнайте, как создать группу Microsoft 365 с заданным предпочтительным расположением данных в многоэтабной среде.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086828"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a><span data-ttu-id="76c11-103">Создание группы Microsoft 365 с определенным предпочтительным расположением данных</span><span class="sxs-lookup"><span data-stu-id="76c11-103">Create a Microsoft 365 Group with a specific preferred data location</span></span>

<span data-ttu-id="76c11-104">Когда пользователи в многоэтапной среде создают группу Microsoft 365, предпочтительное расположение данных группы (PDL) автоматически задается для расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="76c11-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location (PDL) is automatically set to that of the user.</span></span> <span data-ttu-id="76c11-105">Глобальные администраторы, администраторы SharePoint и Exchange могут создавать группы в любом выбранном регионе.</span><span class="sxs-lookup"><span data-stu-id="76c11-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="76c11-106">Если нужно создать группу с определенным PDL, можно использовать Центр администрирования SharePoint или командлет Microsoft PowerShell New-UnifiedGroup для Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="76c11-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="76c11-107">При этом как почтовый ящик группы, так и сайт SharePoint, связанный с группой, подготавливаются в указанном предпочтительном расположении данных (PDL).</span><span class="sxs-lookup"><span data-stu-id="76c11-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="76c11-108">Чтобы создать группу Microsoft 365 с задатким PDL, перейдите в центр администрирования SharePoint в географическом расположении, где необходимо создать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="76c11-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="76c11-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="76c11-109">For example:</span></span>

<span data-ttu-id="76c11-110">Если нужно создать сайт группы в Австралии, вы можете перейти на страницу https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="76c11-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="76c11-111">Нажмите **+ Создать**.</span><span class="sxs-lookup"><span data-stu-id="76c11-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="76c11-112">Следуйте инструкциям, чтобы создать сайт группы.</span><span class="sxs-lookup"><span data-stu-id="76c11-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="76c11-113">Сайт группы будет подготовлен в географическом расположении, соответствующем Центру администрирования SharePoint, из которого вы отправили запрос на создание сайта.</span><span class="sxs-lookup"><span data-stu-id="76c11-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="76c11-114">Использование Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="76c11-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="76c11-115">Подключитесь к Exchange Online PowerShell и передайте параметр *- MailBoxRegion* с кодом региона.</span><span class="sxs-lookup"><span data-stu-id="76c11-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="76c11-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="76c11-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Снимок экрана: командлет PowerShell New-UnifiedGroup с синтаксисом](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="76c11-118">Обратите внимание, что подготовка сайта группы SharePoint выполняется по запросу.</span><span class="sxs-lookup"><span data-stu-id="76c11-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="76c11-119">В первый раз сайт будет подготовлен владельцем группы или участником, пытающимся получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="76c11-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="76c11-120">Коды регионов</span><span class="sxs-lookup"><span data-stu-id="76c11-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="76c11-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="76c11-121">Related topics</span></span>

[<span data-ttu-id="76c11-122">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="76c11-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
