---
title: Назначение лицензий Microsoft 365 учетным записям пользователей
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Описывает, как назначать лицензии Microsoft 365 учетным записям пользователей по отдельности или на основе членства в группе.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051536"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="5977d-103">Назначение лицензий Microsoft 365 учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="5977d-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="5977d-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5977d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5977d-105">Для облачной модели удостоверений можно назначить лицензии Microsoft 365 учетным записям пользователей по мере их создания в зависимости от их создания.</span><span class="sxs-lookup"><span data-stu-id="5977d-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="5977d-106">Для гибридной модели удостоверений, когда учетные записи пользователей Active Directory Domain Services (AD DS) синхронизируются впервые, им автоматически не назначено расположение или лицензия Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5977d-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="5977d-107">**Необходимо настроить каждую учетную запись пользователя с расположением пользователя до или вместе с назначением лицензии.**</span><span class="sxs-lookup"><span data-stu-id="5977d-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="5977d-108">В любом случае необходимо назначить лицензию учетным записям пользователей, чтобы пользователи могли получать доступ к службам Microsoft 365, таким как электронная почта и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5977d-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="5977d-109">Лицензии можно назначать учетным записям пользователей как индивидуально, так и автоматически через членство в группе.</span><span class="sxs-lookup"><span data-stu-id="5977d-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="5977d-110">Чтобы назначить лицензии Microsoft 365 отдельным учетным записям пользователей, можно использовать:</span><span class="sxs-lookup"><span data-stu-id="5977d-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="5977d-111">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5977d-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="5977d-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5977d-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="5977d-113">Центр администрирования Azure AD</span><span class="sxs-lookup"><span data-stu-id="5977d-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="5977d-114">Лицензирование на основе групп</span><span class="sxs-lookup"><span data-stu-id="5977d-114">Group-based licensing</span></span>

<span data-ttu-id="5977d-115">Можно настроить группы безопасности в Azure AD, чтобы автоматически назначать лицензии из набора подписок всем участникам группы.</span><span class="sxs-lookup"><span data-stu-id="5977d-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="5977d-116">Это называется *лицензированием на основе групп*.</span><span class="sxs-lookup"><span data-stu-id="5977d-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="5977d-117">Когда учетная запись добавляется в группу или удаляется из нее, лицензии для подписок группы автоматически назначаются этой учетной записи или отменяются для нее.</span><span class="sxs-lookup"><span data-stu-id="5977d-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="5977d-118">Убедитесь, что у вас есть достаточно лицензий для всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="5977d-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="5977d-119">Если лицензии закончатся, они не будут назначаться новым пользователям, пока эти лицензии не станут доступны.</span><span class="sxs-lookup"><span data-stu-id="5977d-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="5977d-120">Лицензирование на основе групп не следует настраивать для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.</span><span class="sxs-lookup"><span data-stu-id="5977d-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="5977d-121">Дополнительные новости см. в [групповых лицензиях в Azure AD.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="5977d-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5977d-122">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5977d-122">Next steps</span></span>

<span data-ttu-id="5977d-123">С соответствующим набором учетных записей пользователей, которые были назначены лицензии, теперь вы готовы к:</span><span class="sxs-lookup"><span data-stu-id="5977d-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="5977d-124">Реализация безопасности</span><span class="sxs-lookup"><span data-stu-id="5977d-124">Implement security</span></span>](../security/defender-365-security/security-roadmap.md)
- [<span data-ttu-id="5977d-125">Развертывание клиентского программного обеспечения, например Приложений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5977d-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="5977d-126">Настройка управления устройствами</span><span class="sxs-lookup"><span data-stu-id="5977d-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="5977d-127">Настройка служб и приложений</span><span class="sxs-lookup"><span data-stu-id="5977d-127">Configure services and applications</span></span>](configure-services-and-applications.md)