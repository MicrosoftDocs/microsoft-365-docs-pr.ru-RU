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
description: Чтобы пользователи могли управлять функциями безопасности и соответствия требованиям, им должны быть назначены соответствующие разрешения в Центре безопасности & требованиям Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826605"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="5f7c1-103">Предоставление пользователям доступа к Центру безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5f7c1-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="5f7c1-104">Чтобы пользователи могли управлять функциями безопасности и соответствия требованиям, им необходимо назначить им соответствующие разрешения в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="5f7c1-105">Как глобальный администратор или участник группы ролей OrganizationManagement в Центре безопасности & требованиям, вы можете предоставить пользователям эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="5f7c1-106">Пользователи смогут управлять только теми функциями безопасности и соответствия требованиям, к которым вы предоставите им доступ.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="5f7c1-107">Дополнительные сведения о различных разрешениях, предоставляемых пользователям в Центре безопасности &, см. в разделе ["Разрешения" & безопасности.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="5f7c1-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5f7c1-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5f7c1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5f7c1-109">Для выполнения действий, описанных в этой статье, вы должны быть глобальным администратором или членом группы ролей "Управление организацией" в Центре соответствия требованиям &.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="5f7c1-110">Группы ролей для Центра безопасности & могут иметь имена, похожие на имена групп ролей в Exchange Online, но это не одинаковые.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="5f7c1-111">Членство в группе ролей Не является членством в службе Exchange Online и Центром безопасности & центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="5f7c1-112">Партнеры по делегированным доступа (DAP) с разрешениями на администрирование от имени (AOBO) не могут получить доступ к Центру безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="5f7c1-113">Использование Центра администрирования для предоставления другому пользователю доступа к Центру безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5f7c1-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="5f7c1-114">[Войдите в Систему и перейдите в Центр администрирования.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)</span><span class="sxs-lookup"><span data-stu-id="5f7c1-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="5f7c1-115">В Центре администрирования Microsoft 365 откройте Центры администрирования, а **затем** щелкните **"Безопасность & Соответствие требованиям".**</span><span class="sxs-lookup"><span data-stu-id="5f7c1-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="5f7c1-116">В Центре безопасности & выберите раздел **"Разрешения".**</span><span class="sxs-lookup"><span data-stu-id="5f7c1-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="5f7c1-117">В списке выберите группу ролей, в которую необходимо добавить пользователя, и нажмите **значок** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) редактирования.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="5f7c1-118">На странице свойств группы ролей в разделе **"Участники"** нажмите кнопку **"Добавить**значок добавить" и выберите имя ![ ](../../media/ITPro-EAC-AddIcon.gif) пользователя(или пользователей), которых нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="5f7c1-119">Выбрав всех пользователей, которых нужно добавить в группу ролей, нажмите \*\*кнопку "Добавить", \> \*\* а затем **" ОК".**</span><span class="sxs-lookup"><span data-stu-id="5f7c1-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="5f7c1-120">Нажмите кнопку **Сохранить**, чтобы сохранить изменения в группе ролей.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5f7c1-121">Как проверить, что все получилось</span><span class="sxs-lookup"><span data-stu-id="5f7c1-121">How do you know this worked?</span></span>

1. <span data-ttu-id="5f7c1-122">В Центре безопасности & выберите раздел **"Разрешения".**</span><span class="sxs-lookup"><span data-stu-id="5f7c1-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="5f7c1-123">В списке выберите группу ролей, чтобы просмотреть ее участников.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="5f7c1-124">В правой части области сведений о группе ролей можно просматривать список ее членов.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="5f7c1-125">Использование PowerShell для предоставления другому пользователю доступа к Центру безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5f7c1-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="5f7c1-126">[Подключение к интерфейсу PowerShell Центра безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f7c1-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="5f7c1-127">Воспользуйтесь командой **Add-RoleGroupMember**, чтобы добавить пользователя в группу ролей Organization Management (Управление организацией), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="5f7c1-128">**Параметры:**</span><span class="sxs-lookup"><span data-stu-id="5f7c1-128">**Parameters**:</span></span>

   - <span data-ttu-id="5f7c1-129">_Identity_ — это группа ролей, в которую добавляются участники.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="5f7c1-130">_Участник —_ это почтовый ящик, универсальная группа безопасности или компьютер, которые необходимо добавить в группу ролей.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="5f7c1-131">За один раз можно добавить только одного участника.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="5f7c1-132">Дополнительные сведения о синтаксисе и параметрах см. в [статье Add-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="5f7c1-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5f7c1-133">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="5f7c1-133">How do you know this worked?</span></span>

<span data-ttu-id="5f7c1-134">Чтобы проверить, что вы даете пользователям доступ к Центру безопасности &, используйте **командлет Get-RoleGroupMember** для просмотра членов в группе ролей Управление организацией (Organization Management) как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5f7c1-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="5f7c1-135">Дополнительные сведения о синтаксисе и параметрах см. в [статье Get-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="5f7c1-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
