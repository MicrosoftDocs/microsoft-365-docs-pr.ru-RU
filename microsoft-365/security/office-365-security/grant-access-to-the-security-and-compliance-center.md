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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Пользователям должны быть назначены разрешения в Центре безопасности и & соответствия требованиям Microsoft 365, прежде чем они смогут управлять любыми функциями обеспечения безопасности и соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289881"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="ab037-103">Предоставление пользователям доступа к Центру безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ab037-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ab037-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ab037-104">**Applies to**</span></span>
- [<span data-ttu-id="ab037-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ab037-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ab037-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ab037-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ab037-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab037-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ab037-108">Пользователям должны быть назначены разрешения в Центре безопасности & соответствия требованиям, прежде чем они смогут управлять функциями безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab037-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="ab037-109">Как глобальный администратор или участник группы ролей OrganizationManagement в Центре безопасности & соответствия требованиям, вы можете предоставить эти разрешения пользователям.</span><span class="sxs-lookup"><span data-stu-id="ab037-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="ab037-110">Пользователи смогут управлять только теми функциями безопасности и соответствия требованиям, к которым вы предоставите им доступ.</span><span class="sxs-lookup"><span data-stu-id="ab037-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="ab037-111">Дополнительные сведения о различных разрешениях, которые можно предоставить пользователям в Центре безопасности & соответствия требованиям, можно найти в Центре безопасности [& соответствия требованиям.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="ab037-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ab037-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ab037-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ab037-113">Для выполнения действий, которые необходимо выполнить в этой статье, необходимо быть глобальным администратором или членом группы ролей OrganizationManagement в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab037-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="ab037-114">Группы ролей для Центра & соответствия требованиям могут иметь похожие имена на группы ролей в Exchange Online, но они не одинаковы.</span><span class="sxs-lookup"><span data-stu-id="ab037-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="ab037-115">Членство в группах ролей не совместно с Exchange Online и Центром безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab037-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="ab037-116">Партнеры службы разрешений делегирования доступа (DAP) с разрешениями администрирования от имени (AOBO) не могут получить доступ к Центру безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ab037-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="ab037-117">Использование Центра безопасности & соответствия требованиям для того, чтобы предоставить другому пользователю доступ к Центру & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ab037-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="ab037-118">Откройте Центр безопасности & соответствия требованиям и <https://protection.office.com> перейдите к **центру разрешений.**</span><span class="sxs-lookup"><span data-stu-id="ab037-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="ab037-119">Чтобы перейти непосредственно на **вкладку "Разрешения",** откройте <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="ab037-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="ab037-120">В списке групп ролей выберите группу ролей  и нажмите значок ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) редактирования.</span><span class="sxs-lookup"><span data-stu-id="ab037-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="ab037-121">На странице свойств группы ролей в группе "Участники" щелкните значок добавления и выберите имя пользователя ![ (или пользователей), которого вы хотите ](../../media/ITPro-EAC-AddIcon.gif) добавить.</span><span class="sxs-lookup"><span data-stu-id="ab037-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="ab037-122">Выбрав всех пользователей, которые нужно добавить в группу ролей, нажмите кнопку **"Добавить" \>** и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="ab037-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="ab037-123">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab037-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="ab037-124">Использование PowerShell Центра & безопасности для обеспечения доступа других пользователей к Центру безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ab037-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="ab037-125">[Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ab037-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="ab037-126">Используйте указанный ниже синтаксис.</span><span class="sxs-lookup"><span data-stu-id="ab037-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="ab037-127">Дополнительные сведения о синтаксисах и параметрах см. в описании [add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="ab037-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ab037-128">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="ab037-128">How do you know this worked?</span></span>

<span data-ttu-id="ab037-129">Чтобы убедиться, что вы успешно предоставили доступ к Центру безопасности & соответствия требованиям, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ab037-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="ab037-130">В Центре безопасности & соответствия требованиям перейдите в **"Разрешения"** и выберите группу ролей.</span><span class="sxs-lookup"><span data-stu-id="ab037-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="ab037-131">В открываемом окле сведений проверьте членов группы ролей.</span><span class="sxs-lookup"><span data-stu-id="ab037-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="ab037-132">В PowerShell центра & безопасности замените имя группы ролей и запустите \<RoleGroupName\> следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab037-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="ab037-133">Подробные сведения о синтаксисах и параметрах см. в описании [get-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="ab037-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
