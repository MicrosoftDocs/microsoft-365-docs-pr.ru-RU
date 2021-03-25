---
title: Использование базовых разрешений для доступа к Центру безопасности Защитника Майкрософт
description: Узнайте, как использовать основные разрешения для доступа к порталу Microsoft Defender для конечных точек.
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
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163675"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="c98c4-104">Использование базовых разрешений для доступа к порталу</span><span class="sxs-lookup"><span data-stu-id="c98c4-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c98c4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c98c4-105">**Applies to:**</span></span>
- <span data-ttu-id="c98c4-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c98c4-106">Azure Active Directory</span></span>
- [<span data-ttu-id="c98c4-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c98c4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c98c4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c98c4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c98c4-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c98c4-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c98c4-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c98c4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="c98c4-111">Обратитесь к инструкциям ниже, чтобы использовать управление базовыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="c98c4-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="c98c4-112">Вы можете использовать любой из следующих решений:</span><span class="sxs-lookup"><span data-stu-id="c98c4-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="c98c4-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c98c4-113">Azure PowerShell</span></span>
- <span data-ttu-id="c98c4-114">Портал Azure</span><span class="sxs-lookup"><span data-stu-id="c98c4-114">Azure portal</span></span>

<span data-ttu-id="c98c4-115">Для детального контроля над разрешениями [переключение на](rbac.md)управление доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="c98c4-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="c98c4-116">Назначение доступа пользователей с помощью Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c98c4-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="c98c4-117">Вы можете назначить пользователям один из следующих уровней разрешений:</span><span class="sxs-lookup"><span data-stu-id="c98c4-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="c98c4-118">Полный доступ (чтение и записи)</span><span class="sxs-lookup"><span data-stu-id="c98c4-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="c98c4-119">Доступ только для чтения</span><span class="sxs-lookup"><span data-stu-id="c98c4-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="c98c4-120">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="c98c4-120">Before you begin</span></span>

- <span data-ttu-id="c98c4-121">Установка Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c98c4-121">Install Azure PowerShell.</span></span> <span data-ttu-id="c98c4-122">Дополнительные сведения см. в [рублях "Установка и настройка Azure PowerShell".](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)</span><span class="sxs-lookup"><span data-stu-id="c98c4-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="c98c4-123">Необходимо выполнить командлеты PowerShell в повышенной командной строке.</span><span class="sxs-lookup"><span data-stu-id="c98c4-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="c98c4-124">Подключение к вашему Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c98c4-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="c98c4-125">Дополнительные сведения см. в [дополнительных сведениях в connect-MsolService.](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="c98c4-125">For more information, see [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="c98c4-126">**Полный доступ**</span><span class="sxs-lookup"><span data-stu-id="c98c4-126">**Full access**</span></span> <br>
<span data-ttu-id="c98c4-127">Пользователи с полным доступом могут войти в систему, просмотреть всю системную информацию и разрешить оповещения, отправить файлы для глубокого анализа и скачать бортовой пакет.</span><span class="sxs-lookup"><span data-stu-id="c98c4-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="c98c4-128">Назначение прав на полный доступ требует добавления пользователей в встроенные роли AAD "Администратор безопасности" или "Глобальный администратор".</span><span class="sxs-lookup"><span data-stu-id="c98c4-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="c98c4-129">**Доступ только для чтения**</span><span class="sxs-lookup"><span data-stu-id="c98c4-129">**Read-only access**</span></span> <br>
<span data-ttu-id="c98c4-130">Пользователи с доступом только для чтения могут войти в систему, просмотреть все оповещения и связанные сведения.</span><span class="sxs-lookup"><span data-stu-id="c98c4-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="c98c4-131">Они не смогут изменять состояния оповещений, отправлять файлы для глубокого анализа или выполнять операции по изменению состояния.</span><span class="sxs-lookup"><span data-stu-id="c98c4-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="c98c4-132">Назначение прав доступа только для чтения требует добавления пользователей в встроенную роль Azure AD azure.</span><span class="sxs-lookup"><span data-stu-id="c98c4-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="c98c4-133">Чтобы назначить роли безопасности, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c98c4-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="c98c4-134">Для **чтения и записи** назначьте пользователям роль администратора безопасности с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c98c4-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="c98c4-135">Для **доступа только для** чтения назначьте пользователям роль читателя безопасности с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c98c4-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="c98c4-136">Дополнительные сведения см. в [добавлении или удалите членов группы с помощью Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="c98c4-136">For more information, see [Add or remove group members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="c98c4-137">Назначение доступа пользователей с помощью портала Azure</span><span class="sxs-lookup"><span data-stu-id="c98c4-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="c98c4-138">Дополнительные сведения см. в ссылке Назначение ролей администратора и не администратора [пользователям с Помощью Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="c98c4-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="c98c4-139">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="c98c4-139">Related topic</span></span>

- [<span data-ttu-id="c98c4-140">Управление доступом к порталу с помощью RBAC</span><span class="sxs-lookup"><span data-stu-id="c98c4-140">Manage portal access using RBAC</span></span>](rbac.md)