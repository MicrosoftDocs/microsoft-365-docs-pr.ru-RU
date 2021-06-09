---
title: Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: Узнайте, как управлять Microsoft 365 учетными записями, лицензиями и группами с помощью PowerShell.
ms.openlocfilehash: d3745b9365c67615efe32881408d1a717b8dbbed
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371540"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="384e9-103">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="384e9-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="384e9-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="384e9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="384e9-105">Microsoft 365 администраторы должны управлять учетной записью, лицензиями и группами пользователей.</span><span class="sxs-lookup"><span data-stu-id="384e9-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="384e9-106">Хотя большинство этих задач можно выполнять в центре администрирования Microsoft 365, некоторые из них проще выполнять в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="384e9-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="384e9-107">Дополнительные сведения см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="384e9-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="384e9-108">Учетные записи пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-108">User accounts</span></span>

- [<span data-ttu-id="384e9-109">Создание учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-110">Просмотр учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-111">Настройка свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="384e9-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-112">Назначение ролей учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-113">Удаление и восстановление учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-114">Блокировка учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-115">Пароли</span><span class="sxs-lookup"><span data-stu-id="384e9-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="384e9-116">Лицензии и службы</span><span class="sxs-lookup"><span data-stu-id="384e9-116">Licenses and services</span></span>
- [<span data-ttu-id="384e9-117">Просмотр лицензий и служб</span><span class="sxs-lookup"><span data-stu-id="384e9-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-118">Просмотр лицензированных и нелицензированных пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-119">Назначение лицензий учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-120">Просмотр сведений о лицензии и службе учетной записи</span><span class="sxs-lookup"><span data-stu-id="384e9-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-121">Отключение доступа к службам</span><span class="sxs-lookup"><span data-stu-id="384e9-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="384e9-122">Отключение доступа к Sway</span><span class="sxs-lookup"><span data-stu-id="384e9-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="384e9-123">Отключение доступа к службам во время назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="384e9-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="384e9-124">Удаление лицензий из учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="384e9-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="384e9-125">Группы</span><span class="sxs-lookup"><span data-stu-id="384e9-125">Groups</span></span>
- [<span data-ttu-id="384e9-126">Управление группами безопасности</span><span class="sxs-lookup"><span data-stu-id="384e9-126">Manage security groups</span></span>](manage-security-groups-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-127">Управление участием в группах безопасности</span><span class="sxs-lookup"><span data-stu-id="384e9-127">Maintain security group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="384e9-128">Управление группами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="384e9-128">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
