---
title: Доступ к порталу администрирования
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146275"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="29de6-103">Доступ к порталу администрирования</span><span class="sxs-lookup"><span data-stu-id="29de6-103">Access the admin portal</span></span>

<span data-ttu-id="29de6-104">Ваш шлюз к службе управляемых рабочих столов Майкрософт — портал Microsoft [Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="29de6-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="29de6-105">Дополнительные сведения об использовании и настройке взаимодействия с порталом Azure см. в [документации по порталу Azure](https://docs.microsoft.com/azure/azure-portal/).</span><span class="sxs-lookup"><span data-stu-id="29de6-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> 

<span data-ttu-id="29de6-106">Учетная запись администратора должна иметь специальные разрешения для доступа к порталу администрирования настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-106">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="29de6-107">Вы можете управлять административным доступом к этим функциям в Организации с помощью управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="29de6-107">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="29de6-108">Дополнительные сведения о ролях Azure Active Directory приведены в статье [разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="29de6-108">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="29de6-109">Назначьте учетные записи пользователя администратора любой из следующих ролей, чтобы обеспечить доступ:</span><span class="sxs-lookup"><span data-stu-id="29de6-109">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="29de6-110">Роль Azure AD</span><span class="sxs-lookup"><span data-stu-id="29de6-110">Azure AD role</span></span>  |<span data-ttu-id="29de6-111">Разрешения на Рабочий стол, управляемые корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="29de6-111">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="29de6-112">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="29de6-112">Global Administrator</span></span>     | <span data-ttu-id="29de6-113">Администраторы, которым назначена эта роль, будут иметь **разрешения на чтение и запись** для всех компонентов на портале администрирования рабочих столов, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-113">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="29de6-114">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="29de6-114">Global Reader</span></span>     | <span data-ttu-id="29de6-115">Администраторы с этой ролью будут иметь **разрешения только на чтение** всех компонентов на портале администрирования настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-115">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="29de6-116">Администратор службы Intune</span><span class="sxs-lookup"><span data-stu-id="29de6-116">Intune Service Administrator</span></span>     |  <span data-ttu-id="29de6-117">Администраторы, которым назначена эта роль, будут иметь **разрешения на чтение и запись** для всех компонентов на портале администрирования рабочих столов, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-117">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="29de6-118">Администратор поддержки службы</span><span class="sxs-lookup"><span data-stu-id="29de6-118">Service Support Administrator</span></span>     | <span data-ttu-id="29de6-119">Администраторы, которым назначена эта роль, будут иметь **разрешения на чтение и запись** для всех компонентов на портале администрирования рабочих столов, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="29de6-120">Только роль глобального администратора обладает необходимыми разрешениями для *регистрации* вашей организации в управляемом рабочем столе Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-120">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="29de6-121">Имейте в виду, что роли Azure Active Directory будут предоставлять права учетных записей пользователей в различных службах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="29de6-121">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="29de6-122">После завершения регистрации с помощью управляемого рабочего стола Майкрософт необходимо всегда использовать роль с *минимальными* правами, необходимыми для выполнения других задач.</span><span class="sxs-lookup"><span data-stu-id="29de6-122">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="29de6-123">Назначение ролей администраторам</span><span class="sxs-lookup"><span data-stu-id="29de6-123">Assigning roles to administrators</span></span>

<span data-ttu-id="29de6-124">Если вам нужна помощь в назначении ролей Azure Active Directory, ознакомьтесь [с разрешениями роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="29de6-124">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
