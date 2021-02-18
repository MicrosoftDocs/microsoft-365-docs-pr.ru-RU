---
title: Среда разработки и тестирования изолированного сайта группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: Сводка. Настройте сайт группы SharePoint Online, изолированный от остальной организации в среде тестирования и тестирования Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286613"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="f70e8-103">Среда разработки и тестирования изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f70e8-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f70e8-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f70e8-104">**Applies to**</span></span>
- [<span data-ttu-id="f70e8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f70e8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f70e8-106">Microsoft Defender для Office 365 (план 1)</span><span class="sxs-lookup"><span data-stu-id="f70e8-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="f70e8-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f70e8-107">SharePoint Online</span></span> 


 <span data-ttu-id="f70e8-108">**Сводка:** Настройте сайт группы SharePoint Online, изолированный от остальной организации в среде тестирования и тестирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f70e8-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="f70e8-109">Сайты группы SharePoint Online в Microsoft 365 — это расположения для совместной работы с помощью общей библиотеки документов, записной книжки OneNote и других служб.</span><span class="sxs-lookup"><span data-stu-id="f70e8-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="f70e8-110">Во многих случаях требуется широкий доступ и совместная работа отделов или организаций.</span><span class="sxs-lookup"><span data-stu-id="f70e8-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="f70e8-111">Однако в некоторых случаях необходимо жестко контролировать доступ и разрешения для совместной работы небольшой группы людей.</span><span class="sxs-lookup"><span data-stu-id="f70e8-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="f70e8-112">Доступ к сайтам групп SharePoint Online и возможности пользователей контролируется группами и уровнями разрешений SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f70e8-112">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="f70e8-113">По умолчанию на сайтах SharePoint Online предусмотрено три уровня доступа:</span><span class="sxs-lookup"><span data-stu-id="f70e8-113">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="f70e8-114">**Участники** могут просматривать, создавать и изменять ресурсы на сайте.</span><span class="sxs-lookup"><span data-stu-id="f70e8-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="f70e8-115">**Владельцы** могут полностью контролировать сайт, в том числе изменять разрешения.</span><span class="sxs-lookup"><span data-stu-id="f70e8-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="f70e8-116">**Посетители** могут просматривать ресурсы на сайте.</span><span class="sxs-lookup"><span data-stu-id="f70e8-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="f70e8-117">В этой статье приведены инструкции по настройке изолированного сайта группы SharePoint Online для секретного исследовательского проекта ProjectX.</span><span class="sxs-lookup"><span data-stu-id="f70e8-117">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="f70e8-118">Требования к доступу:</span><span class="sxs-lookup"><span data-stu-id="f70e8-118">The access requirements are:</span></span>

- <span data-ttu-id="f70e8-119">Только участники проекта могут получить доступ к сайту и его содержимому (документам, записной книжке OneNote, страницам), уровни разрешений SharePoint на просмотр и редактирование определяются членством в группе.</span><span class="sxs-lookup"><span data-stu-id="f70e8-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="f70e8-120">Только создатель сайта и члены группы администраторов сайта могут выполнять администрирование сайта, в том числе изменять разрешения на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="f70e8-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="f70e8-121">Существует три этапа настройки изолированного сайта группы SharePoint Online в среде разработки и тестирования Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f70e8-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="f70e8-122">Создайте среду тестирования и тестирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f70e8-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="f70e8-123">Создание пользователей и групп для ProjectX.</span><span class="sxs-lookup"><span data-stu-id="f70e8-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="f70e8-124">Создание сайта группы SharePoint Online для ProjectX и его изоляция.</span><span class="sxs-lookup"><span data-stu-id="f70e8-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="f70e8-125">Щелкните [здесь](https://aka.ms/catlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования в One Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="f70e8-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="f70e8-126">Этап 1. Создание среды разработки и тестирования Microsoft 365 для облегченного или имитируемого предприятия</span><span class="sxs-lookup"><span data-stu-id="f70e8-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="f70e8-127">Если вы просто хотите создать изолированный сайт группы SharePoint Online облегченным способом с минимальными требованиями, следуйте инструкциям на этапах 2 и 3 облегченной базовой [конфигурации.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="f70e8-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="f70e8-128">Если вы хотите создать изолированный сайт группы SharePoint Online в имитированной корпоративной конфигурации, следуйте инструкциям в синхронизации с паролем для тестовой среды [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="f70e8-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f70e8-129">Для создания изолированного сайта SharePoint Online не требуется среда разработчика и тестирования имитированной организации, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f70e8-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="f70e8-130">Она указана здесь, чтобы вы могли протестировать изолированный сайт SharePoint Online и поэкспериментировать с ним в среде, которая представляет типичную среду для организаций.</span><span class="sxs-lookup"><span data-stu-id="f70e8-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="f70e8-131">Этап 2. Создание учетных записей пользователей и групп доступа</span><span class="sxs-lookup"><span data-stu-id="f70e8-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="f70e8-132">Чтобы подключиться к пробной подписке с помощью учетной записи глобального администратора, воспользуйтесь инструкциями в PowerShell для подключения к [Office 365:](../../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="f70e8-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="f70e8-133">Компьютер (для облегченной среды разработчика и тестирования Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="f70e8-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="f70e8-134">Виртуальная машина CLIENT1 (для среды тестирования и тестирования Microsoft 365 для имитированных предприятий).</span><span class="sxs-lookup"><span data-stu-id="f70e8-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="f70e8-135">Чтобы создать группы доступа для сайта группы ProjectX SharePoint Online, в командной Windows Azure Модуля Active Directory для Windows PowerShell командной Windows PowerShell командной Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f70e8-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="f70e8-136">Введите название организации (например, contosotoycompany) и двузначный код страны, а затем выполните следующие команды в командной строке модуля Windows Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f70e8-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="f70e8-137">Запишите в надежном месте пароль, созданный командой **New-MsolUser** для учетной записи ведущего дизайнера.</span><span class="sxs-lookup"><span data-stu-id="f70e8-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="f70e8-138">Выполните следующие команды в командной строке модуля Windows Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f70e8-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="f70e8-139">Запишите в надежном месте пароль, созданный командой **New-MsolUser** для учетной записи ведущего научного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="f70e8-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="f70e8-140">Выполните следующие команды в командной строке модуля Windows Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f70e8-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="f70e8-141">Запишите в надежном месте пароль, созданный командой **New-MsolUser** для учетной записи вице-президента по развитию.</span><span class="sxs-lookup"><span data-stu-id="f70e8-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="f70e8-142">Затем, чтобы добавить новые учетные записи в новые группы доступа, запустите следующие команды PowerShell из Windows Azure модуля Active Directory для Windows PowerShell команд:</span><span class="sxs-lookup"><span data-stu-id="f70e8-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="f70e8-143">Результаты:</span><span class="sxs-lookup"><span data-stu-id="f70e8-143">Results:</span></span>

- <span data-ttu-id="f70e8-144">Группа ProjectX-Members содержит учетные записи ведущим дизайнером и ведущим исследователем</span><span class="sxs-lookup"><span data-stu-id="f70e8-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="f70e8-145">Группа ProjectX-Admins доступа содержит учетную запись глобального администратора для пробной подписки</span><span class="sxs-lookup"><span data-stu-id="f70e8-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="f70e8-146">Группа ProjectX-Viewers содержит учетную запись вице-президент по разработке</span><span class="sxs-lookup"><span data-stu-id="f70e8-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="f70e8-147">На рисунке 1 показаны группы доступа и их членство.</span><span class="sxs-lookup"><span data-stu-id="f70e8-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="f70e8-148">**Рис. 1.**</span><span class="sxs-lookup"><span data-stu-id="f70e8-148">**Figure 1**:</span></span>

![Группы Microsoft 365 и их членство для изолированного сайта группы SharePoint Online](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="f70e8-150">Этап 3. Создание сайта группы SharePoint Online для ProjectX и его изоляция</span><span class="sxs-lookup"><span data-stu-id="f70e8-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="f70e8-151">Чтобы создать сайт группы SharePoint Online для ProjectX, выполните перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f70e8-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="f70e8-152">Используя браузер на локальном компьютере (облегченная конфигурация) или CLIENT1 (конфигурация имитированной организации), во sign in to the Microsoft 365 admin center ( <https://admin.microsoft.com> ) using your global administrator account.</span><span class="sxs-lookup"><span data-stu-id="f70e8-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="f70e8-153">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="f70e8-154">На новой вкладке SharePoint в браузере нажмите **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="f70e8-155">В поле **Имя сайта группы** введите **ProjectX**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-155">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="f70e8-156">В **параметрах конфиденциальности выберите** **"Частный" — доступ к** этому сайту могут получить только участники.</span><span class="sxs-lookup"><span data-stu-id="f70e8-156">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="f70e8-157">В поле **Описание сайта группы** введите **Сайт SharePoint для ProjectX** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="f70e8-158">На панели **Кого вы хотите добавить**? нажмите **Завершить**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="f70e8-159">В новой вкладке **Главная, ProjectX** в браузере, на панели инструментов, щелкните значок параметров и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="f70e8-160">В области **Разрешения для сайта** нажмите **Параметры дополнительных разрешений**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="f70e8-161">В новой вкладке **Разрешения: Project X** в браузере нажмите **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="f70e8-162">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить запросы на доступ** (все три флажка должны быть сняты) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="f70e8-163">Выберите **ProjectX — участники** в списке.</span><span class="sxs-lookup"><span data-stu-id="f70e8-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="f70e8-164">На странице **Пользователи и группы** нажмите кнопку **Создание**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="f70e8-165">В диалоговом окне **Общий доступ** введите **ProjectX-Members**, выберите группу и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="f70e8-166">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="f70e8-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="f70e8-167">Выберите **ProjectX — владельцы** в списке.</span><span class="sxs-lookup"><span data-stu-id="f70e8-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="f70e8-168">На странице **Пользователи и группы** нажмите кнопку **Создание**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="f70e8-169">В диалоговом окне **Общий доступ** введите **ProjectX-Admins**, выберите группу и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="f70e8-170">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="f70e8-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="f70e8-171">Выберите **ProjectX — посетители** в списке.</span><span class="sxs-lookup"><span data-stu-id="f70e8-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="f70e8-172">На странице **Пользователи и группы** нажмите кнопку **Создание**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="f70e8-173">В диалоговом окне **Общий доступ** введите **ProjectX-Viewers**, выберите группу и нажмите **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="f70e8-174">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Главная, ProjectX** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="f70e8-175">Ниже приведены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="f70e8-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="f70e8-176">Группа SharePoint "Участники ProjectX" содержит только группу доступа ProjectX-Members (которая содержит только учетные записи ведущим конструктором и ведущим исследователем) и группу ProjectX (которая содержит только учетную запись глобального администратора).</span><span class="sxs-lookup"><span data-stu-id="f70e8-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="f70e8-177">Группа SharePoint владельцев ProjectX содержит только ProjectX-Admins доступа (которая содержит только учетную запись глобального администратора).</span><span class="sxs-lookup"><span data-stu-id="f70e8-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="f70e8-178">Группа SharePoint посетителей ProjectX содержит только ProjectX-Viewers доступа (которая содержит только учетную запись вице-президент по разработке).</span><span class="sxs-lookup"><span data-stu-id="f70e8-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="f70e8-179">Участники не могут изменять разрешения на уровне сайта (это могут делать только члены группы ProjectX-Admins).</span><span class="sxs-lookup"><span data-stu-id="f70e8-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="f70e8-180">Другие учетные записи пользователей не могут получить доступ к сайту и его ресурсам и запросить доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="f70e8-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="f70e8-181">На рисунке 2 показаны группы SharePoint и их участники.</span><span class="sxs-lookup"><span data-stu-id="f70e8-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="f70e8-182">**Рисунок 2**</span><span class="sxs-lookup"><span data-stu-id="f70e8-182">**Figure 2**</span></span>

![Группы SharePoint Online и их членство для изолированного сайта группы SharePoint Online](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="f70e8-184">Теперь продемонстрируем доступ с помощью учетной записи пользователя "Главный конструктор":</span><span class="sxs-lookup"><span data-stu-id="f70e8-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="f70e8-185">Закройте вкладку **Главная, ProjectX** в браузере и перейдите на вкладку **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="f70e8-186">Щелкните имя глобального администратора и нажмите **Выйти**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="f70e8-187">Во sign in to the Microsoft 365 admin center ( <https://admin.microsoft.com> ) using the Lead Designer account name and its password.</span><span class="sxs-lookup"><span data-stu-id="f70e8-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="f70e8-188">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="f70e8-p106">На новой вкладке **SharePoint** введите **ProjectX** в поле поиска, активируйте поиск и выберите сайт группы **ProjectX**. Сайт группы ProjectX откроется на новой вкладке в браузере.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="f70e8-p107">Щелкните значок параметров. Обратите внимание, что параметр **Разрешения для сайта** отсутствует, так как только члены группы ProjectX-Admins могут изменять разрешения для сайта.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="f70e8-194">Откройте приложение "Блокнот" или другой текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="f70e8-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="f70e8-195">Скопируйте URL-адрес сайта группы ProjectX и вставьте его в новой строке в приложении "Блокнот" или другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="f70e8-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="f70e8-196">На новой вкладке **Главная, ProjectX** в браузере нажмите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="f70e8-197">Скопируйте URL-адрес папки документов ProjectX и вставьте его в новой строке в Блокноте или другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="f70e8-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="f70e8-198">В новой вкладке **ProjectX — Документы** в браузере нажмите **Создать > Документ Word**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="f70e8-199">Введите текст на странице, подождите, пока состояние будет указано **"Сохранено",** нажмите кнопку "Назад" в браузере и обновите страницу.</span><span class="sxs-lookup"><span data-stu-id="f70e8-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="f70e8-200">В папке **Документы** появится новый файл **Документ.docx**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="f70e8-201">Щелкните многоязыкDocument.docx **документа** и нажмите кнопку **"Получить ссылку".**</span><span class="sxs-lookup"><span data-stu-id="f70e8-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="f70e8-202">Скопируйте URL-адрес в диалоговом окне "Поделиться Document.docx" и **вберите** его в новую строку в Блокноте или текстовом редакторе, а затем закройте диалоговое окно "Поделиться Document.docx". </span><span class="sxs-lookup"><span data-stu-id="f70e8-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="f70e8-203">Закройте вкладки **ProjectX — Документы** и **SharePoint** в браузере и перейдите на вкладку **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="f70e8-204">Щелкните имя **ведущего дизайнера** и нажмите **Выйти**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="f70e8-205">Теперь продемонстрируем доступ с помощью учетной записи вице-президент по разработке:</span><span class="sxs-lookup"><span data-stu-id="f70e8-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="f70e8-206">Во sign in to the Microsoft 365 admin center ( <https://admin.microsoft.com> ) using the Development VP account name and its password.</span><span class="sxs-lookup"><span data-stu-id="f70e8-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="f70e8-207">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="f70e8-p109">На новой вкладке **SharePoint** введите **ProjectX** в поле поиска, активируйте поиск и выберите сайт группы **ProjectX**. Сайт группы ProjectX откроется на новой вкладке в браузере.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="f70e8-210">Нажмите **Документы** и выберите файл **Документ.docx**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="f70e8-p110">Во вкладке **Документ.docx** в браузере попробуйте изменить текст. Вы увидите сообщение о том, что **этот документ доступен только для чтения**, так как у учетной записи вице-президента по развитию есть только разрешения на просмотр сайта.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="f70e8-214">Закройте вкладки **Документ.docx**, **ProjectX — Документы** и **SharePoint** в браузере.</span><span class="sxs-lookup"><span data-stu-id="f70e8-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="f70e8-215">Перейдите на вкладку **Домашняя страница Microsoft Office**, щелкните имя **вице-президента по развитию** и нажмите **Выйти**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="f70e8-216">Теперь продемонстрируем доступ с помощью учетной записи пользователя, у нее нет разрешений:</span><span class="sxs-lookup"><span data-stu-id="f70e8-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="f70e8-217">Во sign in to the Microsoft 365 admin center ( <https://admin.microsoft.com> ) using the User 3 account name and its password.</span><span class="sxs-lookup"><span data-stu-id="f70e8-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="f70e8-218">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="f70e8-p111">	В новой вкладке *\*SharePoint** введите *\*ProjectX** в поле поиска и активируйте поиск. Вы увидите сообщение *\*Нет результатов, соответствующих вашим условиям поиска*\*.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="f70e8-p112">Скопируйте URL-адрес сайта ProjectX из открытого Блокнота или другого текстового редактора в адресную строку браузера и нажмите клавишу **Ввод**. Вы увидите страницу **Доступ запрещен**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="f70e8-p113">Скопируйте URL-адрес папки документов ProjectX из Блокнота или другого текстового редактора в адресную строку браузера и нажмите клавишу **Ввод**. Вы увидите страницу **Доступ запрещен**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="f70e8-p114">Скопируйте URL-адрес файла Документ.docx из Блокнота или другого текстового редактора в адресную строку браузера и нажмите клавишу **Ввод**. Вы увидите страницу **Доступ запрещен**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="f70e8-227">Закройте вкладку **SharePoint** в браузере, перейдите на вкладку **Домашняя страница Microsoft Office**, щелкните имя **пользователя 3** и нажмите **Выйти**.</span><span class="sxs-lookup"><span data-stu-id="f70e8-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="f70e8-228">Изолированный сайт SharePoint Online готов к дополнительным экспериментам.</span><span class="sxs-lookup"><span data-stu-id="f70e8-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="f70e8-229">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f70e8-229">Next Step</span></span>

<span data-ttu-id="f70e8-230">Когда вы будете готовы выполнить развертывание изолированного сайта группы SharePoint Online в рабочей среде, просмотрите подробные инструкции из статьи [Разработка изолированного сайта группы SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="f70e8-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f70e8-231">См. также</span><span class="sxs-lookup"><span data-stu-id="f70e8-231">See Also</span></span>

[<span data-ttu-id="f70e8-232">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f70e8-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="f70e8-233">Руководства по лаборатории тестирования для облачных решений</span><span class="sxs-lookup"><span data-stu-id="f70e8-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="f70e8-234">Базовая конфигурация "имитация предприятия"</span><span class="sxs-lookup"><span data-stu-id="f70e8-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="f70e8-235">Простая базовая конфигурация</span><span class="sxs-lookup"><span data-stu-id="f70e8-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="f70e8-236">Центр архитектуры и решений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f70e8-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)