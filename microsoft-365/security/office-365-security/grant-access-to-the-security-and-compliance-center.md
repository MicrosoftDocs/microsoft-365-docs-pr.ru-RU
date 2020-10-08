---
title: Предоставление пользователям доступа к Центру безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Пользователям необходимо назначить разрешения в центре безопасности & Microsoft 365, чтобы они могли управлять любыми функциями обеспечения безопасности или соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202811"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="776f0-103">Предоставление пользователям доступа к Центру безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="776f0-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="776f0-104">Пользователям необходимо назначить разрешения в центре безопасности & соответствия требованиям, прежде чем они смогут управлять любыми функциями обеспечения безопасности или соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="776f0-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="776f0-105">В качестве глобального администратора или члена группы ролей Организатионманажемент в центре безопасности & соответствия требованиям вы можете предоставить эти разрешения пользователям.</span><span class="sxs-lookup"><span data-stu-id="776f0-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="776f0-106">Пользователи смогут управлять только теми функциями безопасности и соответствия требованиям, к которым вы предоставите им доступ.</span><span class="sxs-lookup"><span data-stu-id="776f0-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="776f0-107">Для получения дополнительных сведений о различных разрешениях, которые вы можете предоставить пользователям в центре безопасности & соответствия требованиям, изучите [разрешения в центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="776f0-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="776f0-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="776f0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="776f0-109">Чтобы выполнить действия, описанные в этой статье, необходимо быть глобальным администратором или членом группы ролей Организатионманажемент в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="776f0-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="776f0-110">Группы ролей для центра безопасности & соответствия требованиям могут иметь похожие имена для групп ролей в Exchange Online, но они не совпадают.</span><span class="sxs-lookup"><span data-stu-id="776f0-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="776f0-111">Сведения о членстве в группах ролей не являются общими для Exchange Online и центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="776f0-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="776f0-112">Права на делегированный доступ (с правами администратора) с правами администратора от имени (АОБО) не могут получить доступ к центру безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="776f0-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="776f0-113">Использование центра безопасности & соответствия требованиям для предоставления другому пользователю доступа к центру безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="776f0-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="776f0-114">Откройте центр безопасности & соответствия требованиям <https://protection.office.com> и перейдите к разделу **разрешения**.</span><span class="sxs-lookup"><span data-stu-id="776f0-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="776f0-115">Чтобы перейти непосредственно на вкладку **разрешения** , откройте <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="776f0-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="776f0-116">В списке групп ролей выберите группу ролей, а затем щелкните **изменить** ![ значок редактирования ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="776f0-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="776f0-117">На странице свойств группы ролей в разделе **Участники**нажмите **Добавить** ![ значок Добавить ](../../media/ITPro-EAC-AddIcon.gif) и выберите имя пользователя (или пользователей), которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="776f0-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="776f0-118">Выбрав всех пользователей, которых вы хотите добавить в группу ролей, нажмите кнопку **Add (добавить \> )** , а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="776f0-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="776f0-119">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="776f0-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="776f0-120">Используйте PowerShell центра безопасности & соответствия требованиям, чтобы предоставить другому пользователю доступ к центру безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="776f0-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="776f0-121">[Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="776f0-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="776f0-122">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="776f0-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="776f0-123">Подробные сведения о синтаксисе и параметрах можно найти в статье [Add/RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="776f0-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="776f0-124">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="776f0-124">How do you know this worked?</span></span>

<span data-ttu-id="776f0-125">Чтобы убедиться, что вы успешно предоставили доступ к центру безопасности & соответствия требованиям, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="776f0-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="776f0-126">В центре безопасности & соответствия требованиям перейдите к разделу **разрешения** и выберите группу ролей.</span><span class="sxs-lookup"><span data-stu-id="776f0-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="776f0-127">В открывшемся всплывающем окне сведения проверьте членов группы ролей.</span><span class="sxs-lookup"><span data-stu-id="776f0-127">In the details flyout that opens, verify the members of the role group.</span></span> 

- <span data-ttu-id="776f0-128">В PowerShell центра безопасности & соответствия требованиям замените \<RoleGroupName\> имя группы ролей и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="776f0-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="776f0-129">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="776f0-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
