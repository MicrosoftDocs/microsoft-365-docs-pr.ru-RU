---
title: Шаг 7. Настройка управления удостоверениями
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Обзор и настройка управления удостоверениями для клиента Azure AD.
ms.openlocfilehash: d9a9a63f46230a07b35052a3b02231f7b5315d9e
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302926"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="dcc15-103">Шаг 6. Настройка управления удостоверениями</span><span class="sxs-lookup"><span data-stu-id="dcc15-103">Step 6: Configure identity governance</span></span>

![Этап 2. Удостоверения](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="dcc15-105">Управление удостоверениями заключается в защите, контроле и проверке доступа к важным ресурсам с обеспечением производительности сотрудников.</span><span class="sxs-lookup"><span data-stu-id="dcc15-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="dcc15-106">Например, с помощью управления удостоверениями вы можете обеспечить соответствующим пользователям подходящий доступ к нужным ресурсам и определить, изменяется ли этот доступ со временем.</span><span class="sxs-lookup"><span data-stu-id="dcc15-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="dcc15-107">Дополнительные сведения об управлении удостоверениями для Azure Active Directory (Azure AD) см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="dcc15-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="dcc15-108">*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*</span><span class="sxs-lookup"><span data-stu-id="dcc15-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="dcc15-109">Настройка проверок доступа Azure AD</span><span class="sxs-lookup"><span data-stu-id="dcc15-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="dcc15-110">*Это необязательная процедура, применимая только к версии Microsoft 365 корпоративный E5*</span><span class="sxs-lookup"><span data-stu-id="dcc15-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="dcc15-111">На этом этапе вы настроите проверки доступа Azure AD, позволяющие проверять доступ пользователя, чтобы сохранять доступ только для соответствующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="dcc15-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="dcc15-112">Например:</span><span class="sxs-lookup"><span data-stu-id="dcc15-112">For example:</span></span>

- <span data-ttu-id="dcc15-113">При добавлении нового сотрудника в организацию требуется предоставить ему нужный доступ для эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="dcc15-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="dcc15-114">Когда сотрудник переходит в другие команды, расположения или отделы, при необходимости требуется удалять его разрешение на доступ к предыдущим командам, расположениям и отделам.</span><span class="sxs-lookup"><span data-stu-id="dcc15-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="dcc15-115">Когда сотрудник или гость покидает организацию, требуется удалить его разрешение на доступ.</span><span class="sxs-lookup"><span data-stu-id="dcc15-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="dcc15-116">Это особенно важно, если в организации проводятся аудиты безопасности, чтобы определить, обладают ли учетные записи пользователей излишними правами доступа, что может привести к наложению штрафов при нарушении отраслевых или региональных нормативов.</span><span class="sxs-lookup"><span data-stu-id="dcc15-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="dcc15-117">Дополнительные сведения о проверках доступа Azure AD см. в [этой статье](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="dcc15-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="dcc15-118">Azure AD Privileged Identity Management (PIM) предоставляет целый ряд средств управления, предназначенных для защиты прав доступа к ресурсам в AAD, Azure и других облачных службах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dcc15-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="dcc15-119">Azure AD PIM предоставляет полный набор средств управления, помогающих защитить ресурсы компании, такие как каталог, Office 365 и роли ресурсов Azure.</span><span class="sxs-lookup"><span data-stu-id="dcc15-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="dcc15-120">Как и для других видов доступа, с помощью проверок доступа можно настроить регулярные сертификации прав доступа для всех пользователей с ролями администратора.</span><span class="sxs-lookup"><span data-stu-id="dcc15-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="dcc15-121">Служба Azure AD PIM доступна только в версии E5 Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="dcc15-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="dcc15-122">Сведения о настройке различных типов проверок доступа см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="dcc15-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="dcc15-123">Группы и приложения</span><span class="sxs-lookup"><span data-stu-id="dcc15-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="dcc15-124">Роли Azure AD</span><span class="sxs-lookup"><span data-stu-id="dcc15-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="dcc15-125">Роли ресурсов Azure</span><span class="sxs-lookup"><span data-stu-id="dcc15-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="dcc15-126">Промежуточной контрольной точкой в данном разделе служат [критерии выхода](identity-exit-criteria.md#crit-identity-access-reviews).</span><span class="sxs-lookup"><span data-stu-id="dcc15-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="dcc15-127">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="dcc15-127">Next step</span></span>

[<span data-ttu-id="dcc15-128">Условия, при выполнении которых можно считать инфраструктуру идентификации настроенной</span><span class="sxs-lookup"><span data-stu-id="dcc15-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

