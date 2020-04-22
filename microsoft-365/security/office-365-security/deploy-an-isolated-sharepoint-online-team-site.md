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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Сводка. С помощью этих пошаговых инструкций можно развернуть новый изолированный сайт группы SharePoint Online.
ms.openlocfilehash: e35e380b61a94e08ff25e2e4c4bdfa28a635449e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637632"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="b2de0-103">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b2de0-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="b2de0-104">**Сводка.** С помощью этих пошаговых инструкций можно развернуть новый изолированный сайт группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b2de0-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="b2de0-p101">Эта статья представляет собой пошаговое руководство по созданию и настройке изолированного сайта группы SharePoint Online в Microsoft Office 365. Эти инструкции предполагают использование трех групп SharePoint по умолчанию и соответствующих уровней разрешений (по одной группе доступа на основе Azure Active Directory (AD) для каждого уровня доступа).</span><span class="sxs-lookup"><span data-stu-id="b2de0-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="b2de0-107">Этап 1: создание и заполнение групп доступа к сайту группы</span><span class="sxs-lookup"><span data-stu-id="b2de0-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="b2de0-108">На этом этапе вы создаете три группы доступа на основе Azure AD для трех групп SharePoint по умолчанию и заполняете их соответствующими учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2de0-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2de0-p102">При выполнении последующих шагов предполагается, что все необходимые учетные записи пользователей уже существуют и для них назначены соответствующие лицензии. Если это не сделано, завершите требуемые действия, прежде чем переходить к шагу 1.</span><span class="sxs-lookup"><span data-stu-id="b2de0-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="b2de0-111">Шаг 1. Составление списка администраторов сайта SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b2de0-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="b2de0-112">Определите набор учетных записей пользователей для администраторов изолированного сайта группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b2de0-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="b2de0-113">Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365 и хотите использовать Windows PowerShell, создайте список имен участников-пользователей (UPN) (пример имени участника-пользователя: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b2de0-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="b2de0-114">Шаг 2. Составление списка участников сайта</span><span class="sxs-lookup"><span data-stu-id="b2de0-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="b2de0-115">Определите набор учетных записей пользователей для участников изолированного сайта группы, т. е. для тех, кто будет совместно работать с ресурсами, хранящимися на сайте.</span><span class="sxs-lookup"><span data-stu-id="b2de0-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="b2de0-116">Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365 и хотите использовать PowerShell, создайте список их UPN.</span><span class="sxs-lookup"><span data-stu-id="b2de0-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="b2de0-117">Если на сайте много участников, вы можете сохранить список имен участников-пользователей в текстовом файле и добавить их все с помощью одной команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2de0-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="b2de0-118">Шаг 3. Составление списка посетителей сайта</span><span class="sxs-lookup"><span data-stu-id="b2de0-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="b2de0-119">Определите набор учетных записей пользователей для посетителей изолированного сайта группы, т. е. для тех, кто может просматривать ресурсы, хранящиеся на сайте, но не может изменять их или напрямую совместно работать с их содержимым.</span><span class="sxs-lookup"><span data-stu-id="b2de0-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="b2de0-120">Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365 и хотите использовать PowerShell, создайте список их UPN.</span><span class="sxs-lookup"><span data-stu-id="b2de0-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="b2de0-121">Если на сайте много участников, вы можете сохранить список имен участников-пользователей в текстовом файле и добавить их все с помощью одной команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2de0-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="b2de0-122">Читателями сайта могут быть руководители, юрисконсульты или межведомственные заинтересованные лица.</span><span class="sxs-lookup"><span data-stu-id="b2de0-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="b2de0-123">Шаг 4. Создание трех групп доступа для сайта в Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2de0-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="b2de0-124">Вам нужно создать в Azure AD следующие группы доступа:</span><span class="sxs-lookup"><span data-stu-id="b2de0-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="b2de0-125">Администраторы сайта (список из шага 1)</span><span class="sxs-lookup"><span data-stu-id="b2de0-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="b2de0-126">Участники сайта (список из шага 2)</span><span class="sxs-lookup"><span data-stu-id="b2de0-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="b2de0-127">Читатели сайта (список из шага 3)</span><span class="sxs-lookup"><span data-stu-id="b2de0-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="b2de0-128">В браузере перейдите на портал Azure [https://portal.azure.com](https://portal.azure.com) и войдите, используя учетные данные, назначенные администратором управления пользователями или ролью администратора организации.</span><span class="sxs-lookup"><span data-stu-id="b2de0-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="b2de0-129">На портале Azure выберите **Azure Active Directory > Группы**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="b2de0-130">В колонке **Группы — Все группы** выберите пункт **+ Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="b2de0-131">В новой колонке **группы** :</span><span class="sxs-lookup"><span data-stu-id="b2de0-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="b2de0-132">В разделе **Тип группы** выберите **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="b2de0-133">Введите имя группы в поле **имя**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="b2de0-134">Введите описание группы в поле **Описание группы**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="b2de0-135">Выберите **Назначенные** в поле **Тип членства**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="b2de0-136">Нажмите кнопку **Создать**, а затем закройте колонку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="b2de0-137">Повторите шаги 3-5 для дополнительных групп.</span><span class="sxs-lookup"><span data-stu-id="b2de0-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2de0-138">Для создания групп с включенными функциями Office необходимо использовать портал Azure.</span><span class="sxs-lookup"><span data-stu-id="b2de0-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="b2de0-139">Если изолированный сайт SharePoint Online позже настраивается как сайт с строго конфиденциальной информацией с меткой Azure Information Protection для шифрования файлов и назначения разрешений определенным группам, разрешенные группы должны быть созданы с включенными функциями Office.</span><span class="sxs-lookup"><span data-stu-id="b2de0-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="b2de0-140">После создания группы Azure AD невозможно изменить параметр компонентов Office для группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b2de0-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="b2de0-141">Ниже показана итоговая конфигурация с тремя группами доступа к сайту.</span><span class="sxs-lookup"><span data-stu-id="b2de0-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![Три группы доступа для развертывания изолированного сайта SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="b2de0-143">Этап 5.</span><span class="sxs-lookup"><span data-stu-id="b2de0-143">Step 5.</span></span> <span data-ttu-id="b2de0-144">Добавление учетных записей пользователей в группы доступа</span><span class="sxs-lookup"><span data-stu-id="b2de0-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="b2de0-145">На этом шаге выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b2de0-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="b2de0-146">Добавьте список пользователей из шага 1 в группу доступа для администраторов сайта.</span><span class="sxs-lookup"><span data-stu-id="b2de0-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="b2de0-147">Добавьте список пользователей из шага 2 в группу доступа для участников сайта.</span><span class="sxs-lookup"><span data-stu-id="b2de0-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="b2de0-148">Добавьте список пользователей из шага 3 в группу доступа для читателей сайта.</span><span class="sxs-lookup"><span data-stu-id="b2de0-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="b2de0-149">Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory (AD DS), добавьте пользователей в соответствующие группы доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2de0-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="b2de0-150">Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2de0-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="b2de0-151">Если у вас есть дублирующиеся имена групп для любой группы доступа, следует использовать центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2de0-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="b2de0-152">Для центра администрирования Microsoft 365 войдите в систему, используя учетную запись пользователя, которой назначена роль администратора учетных записей или администратора организации, и используйте группы, чтобы добавить соответствующие учетные записи пользователей и группы в соответствующие группы доступа.</span><span class="sxs-lookup"><span data-stu-id="b2de0-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="b2de0-153">Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b2de0-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="b2de0-154">Затем используйте следующий блок команд для добавления отдельной учетной записи пользователя в группу доступа:</span><span class="sxs-lookup"><span data-stu-id="b2de0-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="b2de0-155">Если вы сохранили имена участников-пользователей для учетных записей пользователей какой-либо из групп доступа в текстовом файле, воспользуйтесь следующим блоком команд PowerShell, чтобы добавить их все сразу:</span><span class="sxs-lookup"><span data-stu-id="b2de0-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="b2de0-156">Для добавления отдельной группы в группу доступа PowerShell используйте следующий блок команд:</span><span class="sxs-lookup"><span data-stu-id="b2de0-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="b2de0-157">Результаты должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b2de0-157">The results should be the following:</span></span>
  
- <span data-ttu-id="b2de0-158">Группа Azure AD "Администраторы сайта" содержит учетные записи пользователей или группы администраторов сайта</span><span class="sxs-lookup"><span data-stu-id="b2de0-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="b2de0-159">Группа Azure AD "Участники сайта" содержит учетные записи пользователей или группы участников сайта.</span><span class="sxs-lookup"><span data-stu-id="b2de0-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="b2de0-160">Группа Azure AD для посетителей сайта содержит учетные записи пользователей или группы, которые могут просматривать только содержимое сайта.</span><span class="sxs-lookup"><span data-stu-id="b2de0-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="b2de0-161">Проверяйте список участников группы для каждой группы доступа с помощью центра администрирования Microsoft 365 или с помощью следующего блока команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b2de0-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="b2de0-162">Ниже показана итоговая конфигурация с тремя группами доступа к сайтам, заполненными учетными записями пользователей или группами.</span><span class="sxs-lookup"><span data-stu-id="b2de0-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![Три группы доступа, заполненные учетными записями пользователей.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="b2de0-164">Этап 2. Создание и настройка изолированного сайта группы</span><span class="sxs-lookup"><span data-stu-id="b2de0-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="b2de0-165">На этом этапе вы создаете изолированный сайт SharePoint Online и настраиваете разрешения в соответствии с уровнями разрешений SharePoint Online по умолчанию, чтобы можно было использовать ваши новые группы доступа на основе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b2de0-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="b2de0-166">По умолчанию новые сайты групп включают группу Microsoft 365 и другие связанные ресурсы, но в этом случае мы создадим сайт группы без группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2de0-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="b2de0-167">Это позволяет полностью управлять разрешениями в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b2de0-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="b2de0-168">Сначала создайте сайт группы SharePoint Online, следуя приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="b2de0-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="b2de0-169">Войдите в центр администрирования Microsoft 365 с помощью учетной записи, которая также будет использоваться для администрирования сайта группы SharePoint Online (администратор SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="b2de0-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="b2de0-170">Дополнительные сведения см. в статье [Вход в Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="b2de0-170">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="b2de0-171">В центре администрирования Microsoft 365 в разделе **центры администрирования**щелкните **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="b2de0-172">В центре администрирования SharePoint разверните узел **сайты** и выберите пункт **активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="b2de0-173">Нажмите кнопку **создать**, а затем выберите **другие параметры**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="b2de0-174">В списке **выберите шаблон** выберите пункт **сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="b2de0-175">В поле **имя сайта**введите имя сайта группы.</span><span class="sxs-lookup"><span data-stu-id="b2de0-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="b2de0-176">В поле **основной администратор**введите учетную запись, с которой вы вошли в систему.</span><span class="sxs-lookup"><span data-stu-id="b2de0-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="b2de0-177">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-177">Click **Finish**.</span></span>
    
<span data-ttu-id="b2de0-178">Далее настройте разрешения на новом сайте группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b2de0-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="b2de0-179">На панели инструментов щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="b2de0-180">В разделе **общий доступ к сайту**щелкните ссылку **изменение способа совместного использования участниками**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="b2de0-181">Выберите **только те владельцы сайтов, которые могут предоставлять общий доступ к файлам, папкам и сайтам**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="b2de0-182">Установите параметр **Разрешить запросы на доступ** к **выходу**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="b2de0-183">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="b2de0-184">В области **разрешения** щелкните **Дополнительные параметры разрешений**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="b2de0-185">На вкладке **разрешения** в браузере щелкните \*\* \<имя сайта> участников\*\* в списке.</span><span class="sxs-lookup"><span data-stu-id="b2de0-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="b2de0-186">В разделе **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="b2de0-187">В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для участников сайта, выберите ее и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="b2de0-188">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="b2de0-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="b2de0-189">В списке выберите \*\* \<имя сайта> владельцев\*\* .</span><span class="sxs-lookup"><span data-stu-id="b2de0-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="b2de0-190">В разделе **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="b2de0-191">В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для администраторов сайта, выберите ее и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="b2de0-192">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="b2de0-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="b2de0-193">Щелкните \*\* \<имя сайта> посетителей\*\* в списке.</span><span class="sxs-lookup"><span data-stu-id="b2de0-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="b2de0-194">В разделе **Пользователи и группы** нажмите **Создание**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="b2de0-195">В диалоговом окне **для предоставления общего доступа к элементу** введите имя группы доступа для читателей сайта, выберите ее и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="b2de0-196">Закройте вкладку браузера **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="b2de0-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="b2de0-197">Ознакомьтесь с результатами настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="b2de0-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="b2de0-198">Группа SharePoint \*\* \<имя сайта> владельцы\*\* содержит группу доступа администраторов сайта, в которой все участники имеют уровень разрешений **полный** доступ.</span><span class="sxs-lookup"><span data-stu-id="b2de0-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="b2de0-199">Группа SharePoint \*\* \<имя сайта> Members\*\* содержит группу доступа "Участники сайта", в которой все участники имеют уровень разрешений " **изменить** ".</span><span class="sxs-lookup"><span data-stu-id="b2de0-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="b2de0-200">Группа SharePoint \*\* \<имя сайта> Посетители\*\* содержит группу доступа посетителей сайта, в которой все участники имеют уровень разрешений **Чтение** .</span><span class="sxs-lookup"><span data-stu-id="b2de0-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="b2de0-201">Участники не могут приглашать других участников, равно как и запрашивать доступ для лиц, не являющихся участниками.</span><span class="sxs-lookup"><span data-stu-id="b2de0-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="b2de0-202">Ниже показана итоговая конфигурация с тремя группами SharePoint для сайта, на котором настроено использование трех групп доступа, заполненных учетными записями пользователей или группами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b2de0-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![Последняя конфигурация изолированного сайта SharePoint Online с группами доступа и учетными записями пользователей.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="b2de0-204">Теперь вы и участники сайта можете совместно работать с его материалами посредством участия в одной из групп доступа.</span><span class="sxs-lookup"><span data-stu-id="b2de0-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="b2de0-205">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="b2de0-205">Next step</span></span>

<span data-ttu-id="b2de0-206">Если вам нужно изменить состав группы доступа к сайту или создать папку документов с особыми разрешениями, см. статью [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="b2de0-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b2de0-207">См. также</span><span class="sxs-lookup"><span data-stu-id="b2de0-207">See Also</span></span>

[<span data-ttu-id="b2de0-208">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b2de0-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="b2de0-209">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b2de0-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="b2de0-210">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b2de0-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



