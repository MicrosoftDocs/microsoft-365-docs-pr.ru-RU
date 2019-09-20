---
title: Шаг 7. Настройка управления удостоверениями
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Обзор и настройка управления удостоверениями для клиента Azure AD.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047362"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="9b75c-103">Шаг 7. Настройка управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="9b75c-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="9b75c-104">Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="9b75c-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="9b75c-105">Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.</span><span class="sxs-lookup"><span data-stu-id="9b75c-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="9b75c-106">Дополнительные сведения об управлении удостоверениями для Azure Active Directory (Azure AD) см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="9b75c-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="9b75c-107">Настройка проверок доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="9b75c-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="9b75c-108">*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*</span><span class="sxs-lookup"><span data-stu-id="9b75c-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9b75c-109">На этом этапе вы настроите проверки доступа Azure AD, позволяющие проверять доступ пользователя, чтобы сохранять доступ только для соответствующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="9b75c-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="9b75c-110">Например:</span><span class="sxs-lookup"><span data-stu-id="9b75c-110">For example:</span></span>

- <span data-ttu-id="9b75c-111">При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="9b75c-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="9b75c-112">Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.</span><span class="sxs-lookup"><span data-stu-id="9b75c-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="9b75c-113">Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.</span><span class="sxs-lookup"><span data-stu-id="9b75c-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="9b75c-114">Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.</span><span class="sxs-lookup"><span data-stu-id="9b75c-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="9b75c-115">Дополнительные сведения о проверках доступа Azure AD см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="9b75c-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="9b75c-116">Сведения о настройке различных типов проверок доступа см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="9b75c-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="9b75c-117">Группы и приложения</span><span class="sxs-lookup"><span data-stu-id="9b75c-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="9b75c-118">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="9b75c-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="9b75c-119">Роли ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="9b75c-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="9b75c-120">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-access-reviews).</span><span class="sxs-lookup"><span data-stu-id="9b75c-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="9b75c-121">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="9b75c-121">Next step</span></span>

[<span data-ttu-id="9b75c-122">Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной</span><span class="sxs-lookup"><span data-stu-id="9b75c-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

