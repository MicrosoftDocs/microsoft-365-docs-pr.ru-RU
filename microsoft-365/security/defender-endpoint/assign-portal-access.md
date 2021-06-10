---
title: Назначение доступа пользователя к Центр безопасности в Microsoft Defender
description: Назначить для чтения и записи или чтения только доступ к порталу Microsoft Defender для конечной точки.
keywords: назначение ролей пользователей, назначение доступа к чтением и записи, назначение доступа только для чтения, пользователя, ролей пользователей, ролей
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164781"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="d1c51-104">Назначение доступа пользователя к Центр безопасности в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1c51-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d1c51-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d1c51-105">**Applies to:**</span></span>
- <span data-ttu-id="d1c51-106">Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1c51-106">Azure Active Directory</span></span>
- <span data-ttu-id="d1c51-107">Office 365:</span><span class="sxs-lookup"><span data-stu-id="d1c51-107">Office 365</span></span>
- [<span data-ttu-id="d1c51-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d1c51-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1c51-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1c51-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="d1c51-110">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d1c51-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d1c51-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d1c51-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d1c51-112">Defender for Endpoint поддерживает два способа управления разрешениями:</span><span class="sxs-lookup"><span data-stu-id="d1c51-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="d1c51-113">**Управление базовыми разрешениями.** Установите разрешения для полного доступа или только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d1c51-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="d1c51-114">Управление доступом на основе ролей **(RBAC)**: Установите гранулярные разрешения путем определения ролей, назначения групп пользователей Azure AD к ролям и предоставления группам пользователей доступа к группам устройств.</span><span class="sxs-lookup"><span data-stu-id="d1c51-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="d1c51-115">Дополнительные сведения о RBAC см. в ссылке Управление доступом к порталу с помощью управления доступом на основе [ролей.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="d1c51-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d1c51-116">Если вам уже назначены основные разрешения, вы можете перейти на RBAC в любое время.</span><span class="sxs-lookup"><span data-stu-id="d1c51-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="d1c51-117">Перед переходом рассмотрите следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="d1c51-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="d1c51-118">Пользователям с полным доступом (пользователям, которым назначена роль глобального администратора или администратора безопасности в Azure AD), автоматически назначена роль администратора Defender для конечной точки, которая также имеет полный доступ.</span><span class="sxs-lookup"><span data-stu-id="d1c51-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="d1c51-119">Дополнительные группы пользователей Azure AD могут быть назначены роли администратора Defender для конечной точки после перехода на RBAC.</span><span class="sxs-lookup"><span data-stu-id="d1c51-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="d1c51-120">Управлять разрешениями с помощью RBAC могут только пользователи, назначенные роли администратора Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d1c51-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="d1c51-121">Пользователи с доступом только для чтения (читатели безопасности) будут терять доступ к порталу до тех пор, пока им не будет назначена роль.</span><span class="sxs-lookup"><span data-stu-id="d1c51-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="d1c51-122">Обратите внимание, что роль в RBAC может быть назначена только группам пользователей Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1c51-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="d1c51-123">После перехода на RBAC вы не сможете вернуться к использованию базового управления разрешениями.</span><span class="sxs-lookup"><span data-stu-id="d1c51-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1c51-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d1c51-124">Related topics</span></span>

- [<span data-ttu-id="d1c51-125">Использование основных разрешений для доступа к порталу</span><span class="sxs-lookup"><span data-stu-id="d1c51-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="d1c51-126">Управление доступом к порталу с помощью RBAC</span><span class="sxs-lookup"><span data-stu-id="d1c51-126">Manage portal access using RBAC</span></span>](rbac.md)
