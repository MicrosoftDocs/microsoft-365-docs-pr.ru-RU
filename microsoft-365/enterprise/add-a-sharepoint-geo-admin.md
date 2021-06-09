---
title: Добавление и удаление администратора геообъектов
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Необходимо настроить отдельных администраторов для каждого географического расположения? Узнайте, как добавить или удалить администратора геообъектов в Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905612"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="0aaa7-104">Добавление и удаление администратора геообъектов в Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="0aaa7-105">Можно настроить отдельных администраторов для каждого географического расположения в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="0aaa7-106">Эти администраторы получат доступ к параметрам SharePoint Online и OneDrive, относящимся к конкретным географическим расположениям.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="0aaa7-107">Некоторые службы, например банк терминов, управляются из центрального расположения и копируются в периферийные расположения.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="0aaa7-108">Доступ к ним есть у администратора геообъектов в центральном расположении, но не у администраторов геообъектов в периферийных расположениях.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="0aaa7-109">Глобальные администраторы и администраторы SharePoint Online сохраняют доступ к параметрам в центральном и всех периферийных расположениях.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="0aaa7-110">Настройка администраторов геообъектов</span><span class="sxs-lookup"><span data-stu-id="0aaa7-110">Configuring geo administrators</span></span>

<span data-ttu-id="0aaa7-111">Для настройки администраторов геообъектов требуется модуль PowerShell в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="0aaa7-112">Используйте команду [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) для подключения к центру администрирования геообъекта, для которого нужно добавить администратора. (Например, Connect-SPOService https://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="0aaa7-112">Use [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="0aaa7-113">Чтобы просмотреть существующих администраторов геообъектов в расположении, выполните команду `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="0aaa7-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="0aaa7-114">Добавление пользователя в качестве администратора геообъекта</span><span class="sxs-lookup"><span data-stu-id="0aaa7-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="0aaa7-115">Чтобы добавить пользователя в качестве администратора геообъекта, выполните команду `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="0aaa7-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="0aaa7-116">Чтобы удалить пользователя из администраторов геообъекта в расположении, выполните команду `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="0aaa7-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="0aaa7-117">Добавление группы в качестве администратора геообъекта</span><span class="sxs-lookup"><span data-stu-id="0aaa7-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="0aaa7-118">Можно добавить группу безопасности или группу безопасности с поддержкой электронной почты в качестве администратора геообъекта. (Группы рассылки и группы Microsoft 365 не поддерживаются.)</span><span class="sxs-lookup"><span data-stu-id="0aaa7-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="0aaa7-119">Чтобы добавить группу в качестве администратора геообъекта, выполните команду `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="0aaa7-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="0aaa7-120">Чтобы удалить группу из администраторов геообъекта, выполните команду `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="0aaa7-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="0aaa7-121">Обратите внимание, что не у всех групп безопасности есть псевдоним группы.</span><span class="sxs-lookup"><span data-stu-id="0aaa7-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="0aaa7-122">Если нужно добавить группу безопасности без псевдонима, выполните команду [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) для получения списка групп, найдите ObjectID группы безопасности и выполните команду:</span><span class="sxs-lookup"><span data-stu-id="0aaa7-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="0aaa7-123">Чтобы удалить группу с помощью ObjectID, выполните команду `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="0aaa7-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="0aaa7-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0aaa7-124">Related topics</span></span>

[<span data-ttu-id="0aaa7-125">Add-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="0aaa7-125">Add-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="0aaa7-126">Get-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="0aaa7-126">Get-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="0aaa7-127">Remove-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="0aaa7-127">Remove-SPOGeoAdministrator</span></span>](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="0aaa7-128">Установка псевдонима (MailNickName) для группы безопасности</span><span class="sxs-lookup"><span data-stu-id="0aaa7-128">Set an alias (MailNickName) for a security group</span></span>](/powershell/module/azuread/set-azureadgroup)