---
title: Развертывание изолированного сайта группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Используйте это пошаговые руководства по развертыванию для создания и настройки изолированного сайта группы SharePoint Online в Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165503"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="d9652-103">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9652-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d9652-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="d9652-104">**Applies to**</span></span>
- [<span data-ttu-id="d9652-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="d9652-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="d9652-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9652-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="d9652-107">**Сводка.** С помощью этих пошаговых инструкций можно развернуть новый изолированный сайт группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d9652-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="d9652-p101">Эта статья представляет собой пошаговое руководство по созданию и настройке изолированного сайта группы SharePoint Online в Microsoft Office 365. Эти инструкции предполагают использование трех групп SharePoint по умолчанию и соответствующих уровней разрешений (по одной группе доступа на основе Azure Active Directory (AD) для каждого уровня доступа).</span><span class="sxs-lookup"><span data-stu-id="d9652-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="d9652-110">Этап 1. Создание и заполнение групп доступа к сайту группы</span><span class="sxs-lookup"><span data-stu-id="d9652-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="d9652-111">На этом этапе вы создаете три группы доступа на основе Azure AD для трех групп SharePoint по умолчанию и заполняете их соответствующими учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="d9652-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="d9652-p102">При выполнении последующих шагов предполагается, что все необходимые учетные записи пользователей уже существуют и для них назначены соответствующие лицензии. Если это не сделано, завершите требуемые действия, прежде чем переходить к шагу 1.</span><span class="sxs-lookup"><span data-stu-id="d9652-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="d9652-114">Шаг 1. Составление списка администраторов сайта SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9652-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="d9652-115">Определите набор учетных записей пользователей для администраторов изолированного сайта группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d9652-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="d9652-116">Если вы управляете учетной записью пользователя и группами через Microsoft 365 и хотите использовать Windows PowerShell, со списком их имен участников-пользователей (например, UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d9652-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="d9652-117">Шаг 2. Составление списка участников сайта</span><span class="sxs-lookup"><span data-stu-id="d9652-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="d9652-118">Определите набор учетных записей пользователей для участников изолированного сайта группы, т. е. для тех, кто будет совместно работать с ресурсами, хранящимися на сайте.</span><span class="sxs-lookup"><span data-stu-id="d9652-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="d9652-119">Если вы управляете учетной записью и группами пользователей с помощью Microsoft 365 и хотите использовать PowerShell, соделайте список их upNs.</span><span class="sxs-lookup"><span data-stu-id="d9652-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="d9652-120">Если на сайте много участников, вы можете сохранить список имен участников-пользователей в текстовом файле и добавить их все с помощью одной команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9652-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="d9652-121">Шаг 3. Составление списка посетителей сайта</span><span class="sxs-lookup"><span data-stu-id="d9652-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="d9652-122">Определите набор учетных записей пользователей для посетителей изолированного сайта группы, т. е. для тех, кто может просматривать ресурсы, хранящиеся на сайте, но не может изменять их или напрямую совместно работать с их содержимым.</span><span class="sxs-lookup"><span data-stu-id="d9652-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="d9652-123">Если вы управляете учетной записью и группами пользователей с помощью Microsoft 365 и хотите использовать PowerShell, соделайте список их upNs.</span><span class="sxs-lookup"><span data-stu-id="d9652-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="d9652-124">Если на сайте много участников, вы можете сохранить список имен участников-пользователей в текстовом файле и добавить их все с помощью одной команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9652-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="d9652-125">Читателями сайта могут быть руководители, юрисконсульты или межведомственные заинтересованные лица.</span><span class="sxs-lookup"><span data-stu-id="d9652-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="d9652-126">Шаг 4. Создание трех групп доступа для сайта в Azure AD</span><span class="sxs-lookup"><span data-stu-id="d9652-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="d9652-127">Вам нужно создать в Azure AD следующие группы доступа:</span><span class="sxs-lookup"><span data-stu-id="d9652-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="d9652-128">Администраторы сайта (список из шага 1)</span><span class="sxs-lookup"><span data-stu-id="d9652-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="d9652-129">Участники сайта (список из шага 2)</span><span class="sxs-lookup"><span data-stu-id="d9652-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="d9652-130">Читатели сайта (список из шага 3)</span><span class="sxs-lookup"><span data-stu-id="d9652-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="d9652-131">В браузере перейдите на портал Azure и войдите с помощью учетных данных учетной записи, назначенной с ролью администратора управления пользователями или <https://portal.azure.com> администратора компании.</span><span class="sxs-lookup"><span data-stu-id="d9652-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="d9652-132">На портале Azure выберите **Azure Active Directory > Группы**.</span><span class="sxs-lookup"><span data-stu-id="d9652-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="d9652-133">В колонке **Группы — Все группы** выберите пункт **+ Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="d9652-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="d9652-134">В blade **новой группы:**</span><span class="sxs-lookup"><span data-stu-id="d9652-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="d9652-135">В разделе **Тип группы** выберите **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="d9652-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="d9652-136">Введите имя группы в **имя.**</span><span class="sxs-lookup"><span data-stu-id="d9652-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="d9652-137">Введите описание группы в **описании группы.**</span><span class="sxs-lookup"><span data-stu-id="d9652-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="d9652-138">Выберите **Назначенные** в поле **Тип членства**.</span><span class="sxs-lookup"><span data-stu-id="d9652-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="d9652-139">Нажмите кнопку **Создать**, а затем закройте колонку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="d9652-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="d9652-140">Повторите шаги 3–5 для дополнительных групп.</span><span class="sxs-lookup"><span data-stu-id="d9652-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="d9652-141">Для создания групп необходимо использовать портал Azure, чтобы для них были включены функции Office.</span><span class="sxs-lookup"><span data-stu-id="d9652-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="d9652-142">Если изолированный сайт SharePoint Online позднее настроен как сайт "Строго конфиденциальный" с меткой Azure Information Protection для шифрования файлов и назначения разрешений определенным группам, разрешенные группы должны быть созданы с включенными функциями Office.</span><span class="sxs-lookup"><span data-stu-id="d9652-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="d9652-143">Изменить параметры функций Office для группы Azure AD после ее создания невозможно.</span><span class="sxs-lookup"><span data-stu-id="d9652-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="d9652-144">Ниже приводится итоговая конфигурация с тремя группами доступа к сайту.</span><span class="sxs-lookup"><span data-stu-id="d9652-144">Here is your resulting configuration with the three site access groups.</span></span>

![Три группы доступа для развертывания изолированного сайта SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="d9652-146">Этап 5.</span><span class="sxs-lookup"><span data-stu-id="d9652-146">Step 5.</span></span> <span data-ttu-id="d9652-147">Добавление учетных записей пользователей в группы доступа</span><span class="sxs-lookup"><span data-stu-id="d9652-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="d9652-148">На этом шаге выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d9652-148">In this step, do the following:</span></span>

1. <span data-ttu-id="d9652-149">Добавьте список пользователей из шага 1 в группу доступа администраторов сайта.</span><span class="sxs-lookup"><span data-stu-id="d9652-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="d9652-150">Добавьте список пользователей из шага 2 в группу доступа участников сайта.</span><span class="sxs-lookup"><span data-stu-id="d9652-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="d9652-151">Добавьте список пользователей из шага 3 в группу доступа посетителей сайта.</span><span class="sxs-lookup"><span data-stu-id="d9652-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="d9652-152">Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory (AD DS), добавьте пользователей в соответствующие группы доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9652-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="d9652-153">Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9652-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="d9652-154">Если у вас есть дублирующиеся имена групп для любой из групп доступа, следует использовать Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9652-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="d9652-155">В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span><span class="sxs-lookup"><span data-stu-id="d9652-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="d9652-156">Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="d9652-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="d9652-157">Затем используйте следующий блок команд для добавления отдельной учетной записи пользователя в группу доступа:</span><span class="sxs-lookup"><span data-stu-id="d9652-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="d9652-158">Если вы сохранили имена участников-пользователей для учетных записей пользователей какой-либо из групп доступа в текстовом файле, воспользуйтесь следующим блоком команд PowerShell, чтобы добавить их все сразу:</span><span class="sxs-lookup"><span data-stu-id="d9652-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="d9652-159">Для PowerShell используйте следующий блок команд для добавления отдельной группы в группу доступа:</span><span class="sxs-lookup"><span data-stu-id="d9652-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="d9652-160">Результаты должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9652-160">The results should be the following:</span></span>

- <span data-ttu-id="d9652-161">Группа администраторов сайта Azure AD содержит учетные записи или группы администраторов сайта</span><span class="sxs-lookup"><span data-stu-id="d9652-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="d9652-162">Группа Azure AD для участников сайта содержит учетные записи или группы участников сайта</span><span class="sxs-lookup"><span data-stu-id="d9652-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="d9652-163">Группа "Посетители сайта" в Azure AD содержит учетные записи пользователей или группы, которые могут просматривать только содержимое сайта.</span><span class="sxs-lookup"><span data-stu-id="d9652-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="d9652-164">Проверьте список членов группы для каждой группы доступа в Центре администрирования Microsoft 365 или с помощью следующего блока команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d9652-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="d9652-165">Ниже приводится итоговая конфигурация с тремя группами доступа к сайту, заполненными учетными записями пользователей или группами.</span><span class="sxs-lookup"><span data-stu-id="d9652-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![Три группы доступа, заполненные учетными записями пользователей.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="d9652-167">Этап 2. Создание и настройка изолированного сайта группы</span><span class="sxs-lookup"><span data-stu-id="d9652-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="d9652-168">На этом этапе вы создаете изолированный сайт SharePoint Online и настраиваете разрешения в соответствии с уровнями разрешений SharePoint Online по умолчанию, чтобы можно было использовать ваши новые группы доступа на основе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d9652-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="d9652-169">По умолчанию новые сайты групп включают группу Microsoft 365 и другие связанные ресурсы, но в этом случае мы создадим сайт группы без группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9652-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="d9652-170">Это позволяет полностью поддерживать разрешения через SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d9652-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="d9652-171">Сначала создайте сайт группы SharePoint Online, следуя приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="d9652-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="d9652-172">Во sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span><span class="sxs-lookup"><span data-stu-id="d9652-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="d9652-173">Дополнительные сведения см. в статье [Вход в Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="d9652-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="d9652-174">В Центре администрирования Microsoft 365 в **центре** администрирования щелкните **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="d9652-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="d9652-175">В Центре администрирования SharePoint разйдите раздел **"Сайты"** и щелкните **"Активные сайты".**</span><span class="sxs-lookup"><span data-stu-id="d9652-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="d9652-176">Нажмите **кнопку "Создать"** и выберите **"Другие параметры".**</span><span class="sxs-lookup"><span data-stu-id="d9652-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="d9652-177">В **списке "Выбор шаблона"** выберите сайт **группы.**</span><span class="sxs-lookup"><span data-stu-id="d9652-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="d9652-178">Введите **имя** сайта группы в имени сайта группы.</span><span class="sxs-lookup"><span data-stu-id="d9652-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="d9652-179">Введите **учетную** запись, с помощью учетной записи основного администратора.</span><span class="sxs-lookup"><span data-stu-id="d9652-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="d9652-180">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d9652-180">Click **Finish**.</span></span>

<span data-ttu-id="d9652-181">Далее настройте разрешения на новом сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d9652-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="d9652-182">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="d9652-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="d9652-183">В **разделе "Общий доступ к** сайту" **щелкните "Изменить, как участники могут обмениваться данными".**</span><span class="sxs-lookup"><span data-stu-id="d9652-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="d9652-184">Выберите **"Только владельцы сайта" могут делиться файлами, папками и сайтом.**</span><span class="sxs-lookup"><span data-stu-id="d9652-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="d9652-185">Установите **отключение** запросов **на** доступ.</span><span class="sxs-lookup"><span data-stu-id="d9652-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="d9652-186">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d9652-186">Click **Save**.</span></span>

6. <span data-ttu-id="d9652-187">В области **разрешений** щелкните **параметры дополнительных разрешений.**</span><span class="sxs-lookup"><span data-stu-id="d9652-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="d9652-188">На **вкладке "Разрешения"** браузера щелкните **\<site name> "Члены"** в списке.</span><span class="sxs-lookup"><span data-stu-id="d9652-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="d9652-189">В разделе **Пользователи и группы** нажмите **Создание**.</span><span class="sxs-lookup"><span data-stu-id="d9652-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="d9652-190">В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для участников сайта, выберите ее и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="d9652-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="d9652-191">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="d9652-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="d9652-192">Щелкните **\<site name> "Владельцы"** в списке.</span><span class="sxs-lookup"><span data-stu-id="d9652-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="d9652-193">В разделе **Пользователи и группы** нажмите **Создание**.</span><span class="sxs-lookup"><span data-stu-id="d9652-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="d9652-194">В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для администраторов сайта, выберите ее и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="d9652-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="d9652-195">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="d9652-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="d9652-196">Щелкните **\<site name> "Посетители"** в списке.</span><span class="sxs-lookup"><span data-stu-id="d9652-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="d9652-197">В разделе **Пользователи и группы** нажмите **Создание**.</span><span class="sxs-lookup"><span data-stu-id="d9652-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="d9652-198">В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для читателей сайта, выберите ее и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="d9652-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="d9652-199">Закройте вкладку браузера **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="d9652-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="d9652-200">Ознакомьтесь с результатами настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="d9652-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="d9652-201">Группа **\<site name> SharePoint** владельцев содержит группу доступа администраторов сайта, в которой все участники имеют уровень разрешений **"Полный** доступ".</span><span class="sxs-lookup"><span data-stu-id="d9652-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="d9652-202">Группа **\<site name> SharePoint** "Участники" содержит группу доступа "Участники сайта", в которой все участники имеют уровень разрешений **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="d9652-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="d9652-203">Группа **\<site name> "Посетители** SharePoint" содержит группу доступа посетителей сайта, в которой все участники имеют уровень разрешений  "Чтение".</span><span class="sxs-lookup"><span data-stu-id="d9652-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="d9652-204">Участники не могут приглашать других участников, равно как и запрашивать доступ для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="d9652-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="d9652-205">Ниже приводится итоговая конфигурация с тремя группами SharePoint для сайта, настроенными для использования трех групп доступа, которые заполнены учетными записями пользователей или группами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d9652-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![Окончательная конфигурация изолированного сайта SharePoint Online с группами доступа и учетными записями пользователей.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="d9652-207">Теперь вы и участники сайта можете совместно работать с его материалами посредством участия в одной из групп доступа.</span><span class="sxs-lookup"><span data-stu-id="d9652-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="d9652-208">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="d9652-208">Next step</span></span>

<span data-ttu-id="d9652-209">Если вам нужно изменить состав группы доступа к сайту или создать папку документов с особыми разрешениями, см. статью [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="d9652-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9652-210">См. также</span><span class="sxs-lookup"><span data-stu-id="d9652-210">See Also</span></span>

[<span data-ttu-id="d9652-211">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9652-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="d9652-212">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9652-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="d9652-213">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9652-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
