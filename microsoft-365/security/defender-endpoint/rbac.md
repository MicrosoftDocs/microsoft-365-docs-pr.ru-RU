---
title: Используйте управление доступом на основе ролей для предоставления мелкозернистого доступа к Центр безопасности в Microsoft Defender
description: Создайте роли и группы в операциях безопасности, чтобы предоставить доступ к порталу.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071878"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="5ead3-104">Управление доступом к порталу с помощью управления доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="5ead3-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ead3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5ead3-105">**Applies to:**</span></span>
- <span data-ttu-id="5ead3-106">Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5ead3-106">Azure Active Directory</span></span>
- <span data-ttu-id="5ead3-107">Office 365:</span><span class="sxs-lookup"><span data-stu-id="5ead3-107">Office 365</span></span>

> <span data-ttu-id="5ead3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5ead3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5ead3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5ead3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="5ead3-110">С помощью управления доступом на основе ролей (RBAC) можно создавать роли и группы в группе операций безопасности, чтобы предоставить соответствующий доступ к порталу.</span><span class="sxs-lookup"><span data-stu-id="5ead3-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="5ead3-111">На основе ролей и групп, которые вы создаете, у вас есть тонкий контроль над тем, что пользователи с доступом к порталу могут видеть и делать.</span><span class="sxs-lookup"><span data-stu-id="5ead3-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="5ead3-112">Как правило, крупные группы операций безопасности с распределенной геомагности принимают модель, основанную на уровнях, для назначения и авторизации доступа к порталам безопасности.</span><span class="sxs-lookup"><span data-stu-id="5ead3-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="5ead3-113">Типичные уровни включают следующие три уровня:</span><span class="sxs-lookup"><span data-stu-id="5ead3-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="5ead3-114">Уровень</span><span class="sxs-lookup"><span data-stu-id="5ead3-114">Tier</span></span> | <span data-ttu-id="5ead3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5ead3-115">Description</span></span>
:---|:---
<span data-ttu-id="5ead3-116">Уровень 1</span><span class="sxs-lookup"><span data-stu-id="5ead3-116">Tier 1</span></span> | <span data-ttu-id="5ead3-117">**Локализованная группа операций безопасности / ИТ-группа**</span><span class="sxs-lookup"><span data-stu-id="5ead3-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="5ead3-118">Обычно эта группа проводит проверку и изучает оповещения, содержащиеся в их геолокации, и в случаях, когда требуется активное исправление, передается на уровень 2.</span><span class="sxs-lookup"><span data-stu-id="5ead3-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="5ead3-119">Уровень 2</span><span class="sxs-lookup"><span data-stu-id="5ead3-119">Tier 2</span></span> | <span data-ttu-id="5ead3-120">**Группа региональных операций по безопасности**</span><span class="sxs-lookup"><span data-stu-id="5ead3-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="5ead3-121">Эта группа может видеть все устройства для своего региона и выполнять действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="5ead3-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="5ead3-122">Уровень 3</span><span class="sxs-lookup"><span data-stu-id="5ead3-122">Tier 3</span></span> | <span data-ttu-id="5ead3-123">**Группа глобальных операций по безопасности**</span><span class="sxs-lookup"><span data-stu-id="5ead3-123">**Global security operations team**</span></span> <br> <span data-ttu-id="5ead3-124">Эта группа состоит из экспертов по безопасности и уполномочена видеть и выполнять все действия с портала.</span><span class="sxs-lookup"><span data-stu-id="5ead3-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="5ead3-125">Defender for Endpoint RBAC предназначен для поддержки модели выбора на уровне или на основе ролей, а также позволяет детально контролировать, какие роли можно видеть, к каким устройствам можно получить доступ и какие действия они могут принимать.</span><span class="sxs-lookup"><span data-stu-id="5ead3-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="5ead3-126">Рамки RBAC в центре вокруг следующих элементов управления:</span><span class="sxs-lookup"><span data-stu-id="5ead3-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="5ead3-127">**Управление, которые могут принимать конкретные действия**</span><span class="sxs-lookup"><span data-stu-id="5ead3-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="5ead3-128">Создание настраиваемой роли и управление возможностями Defender для конечных точек, к которые они могут получить доступ с детализацией.</span><span class="sxs-lookup"><span data-stu-id="5ead3-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="5ead3-129">**Управление, которое может видеть сведения о определенных группах устройств или группах**</span><span class="sxs-lookup"><span data-stu-id="5ead3-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="5ead3-130">[Создайте](machine-groups.md) группы устройств по определенным критериям, таким как имена, теги, домены и другие, а затем предоставить им доступ к роли с помощью определенной группы пользователей Azure Active Directory Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ead3-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="5ead3-131">Чтобы реализовать доступ на основе ролей, необходимо определить роли администратора, назначить соответствующие разрешения и назначить группы пользователей Azure AD, назначенные этим ролям.</span><span class="sxs-lookup"><span data-stu-id="5ead3-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="5ead3-132">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5ead3-132">Before you begin</span></span>
<span data-ttu-id="5ead3-133">Перед использованием RBAC важно понимать роли, которые могут предоставлять разрешения, и последствия включаемого RBAC.</span><span class="sxs-lookup"><span data-stu-id="5ead3-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="5ead3-134">Прежде чем включить эту функцию, важно иметь роль глобального администратора или администратора безопасности в Azure AD и чтобы группы Azure AD были готовы к снижению риска блокировки портала.</span><span class="sxs-lookup"><span data-stu-id="5ead3-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="5ead3-135">При первом входе в Центр безопасности в Microsoft Defender доступ предоставляется либо полный доступ, либо только для чтения.</span><span class="sxs-lookup"><span data-stu-id="5ead3-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="5ead3-136">Полный доступ предоставляется пользователям с ролями администратора безопасности или глобального администратора в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ead3-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="5ead3-137">Доступ только к чтению предоставляется пользователям с ролью читателя безопасности в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ead3-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="5ead3-138">Кто-то с ролью администратора Defender for Endpoint Global имеет неограниченный доступ ко всем устройствам, независимо от их объединения групп устройств и назначений групп пользователей Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ead3-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="5ead3-139">Изначально создавать и назначать роли в Центр безопасности в Microsoft Defender смогут только те, у кого есть права глобального администратора Azure AD или администратора безопасности, поэтому важно, чтобы в Azure AD были готовы правильные группы.</span><span class="sxs-lookup"><span data-stu-id="5ead3-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="5ead3-140">**Включение управления доступом на основе ролей приведет к тому, что пользователи с разрешениями только для чтения (например, пользователи, на которые назначена роль читателя службы безопасности Azure AD) будут терять доступ до тех пор, пока они не будут назначены роли.**</span><span class="sxs-lookup"><span data-stu-id="5ead3-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="5ead3-141">Пользователям с разрешениями администратора автоматически назначена встроенная роль глобального администратора Defender for Endpoint с полными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="5ead3-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="5ead3-142">После выбора использования RBAC можно назначить дополнительных пользователей, которые не являются глобальными администраторами Azure AD или администраторами безопасности, в роль глобального администратора Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5ead3-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="5ead3-143">После выбора использования RBAC нельзя вернуться к начальным ролям, как при первом входе на портал.</span><span class="sxs-lookup"><span data-stu-id="5ead3-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="5ead3-144">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="5ead3-144">Related topic</span></span>
- [<span data-ttu-id="5ead3-145">Создание и управление группами устройств в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5ead3-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
