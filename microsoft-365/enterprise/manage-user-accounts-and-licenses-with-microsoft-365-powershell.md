---
title: Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
description: Узнайте, как управлять учетными записями пользователей, лицензиями и группами Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429990"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="eb44c-103">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb44c-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="eb44c-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="eb44c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="eb44c-105">Администратору Microsoft 365 необходимо управлять учетными записями пользователей, лицензиями и группами.</span><span class="sxs-lookup"><span data-stu-id="eb44c-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="eb44c-106">Несмотря на то, что большинство этих задач можно выполнить в центре администрирования Microsoft 365, некоторые из них более просты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb44c-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="eb44c-107">Дополнительные сведения см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="eb44c-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="eb44c-108">Учетные записи пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-108">User accounts</span></span>

- [<span data-ttu-id="eb44c-109">Создание учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-110">Просмотр учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-111">Настройка свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="eb44c-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-112">Назначение ролей учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-113">Удаление и восстановление учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-114">Блокировка учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="eb44c-115">Лицензии и службы</span><span class="sxs-lookup"><span data-stu-id="eb44c-115">Licenses and services</span></span>
- [<span data-ttu-id="eb44c-116">Просмотр лицензий и служб</span><span class="sxs-lookup"><span data-stu-id="eb44c-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-117">Просмотр лицензированных и нелицензированных пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-118">Назначение лицензий учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-119">Просмотр сведений о лицензии и службе учетной записи</span><span class="sxs-lookup"><span data-stu-id="eb44c-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-120">Отключение доступа к службам</span><span class="sxs-lookup"><span data-stu-id="eb44c-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="eb44c-121">Отключение доступа к Sway</span><span class="sxs-lookup"><span data-stu-id="eb44c-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="eb44c-122">Отключение доступа к службам во время назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="eb44c-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="eb44c-123">Удаление лицензий из учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="eb44c-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="eb44c-124">Группы</span><span class="sxs-lookup"><span data-stu-id="eb44c-124">Groups</span></span>
- [<span data-ttu-id="eb44c-125">Управление участием в группах</span><span class="sxs-lookup"><span data-stu-id="eb44c-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="eb44c-126">Управление группами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb44c-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
