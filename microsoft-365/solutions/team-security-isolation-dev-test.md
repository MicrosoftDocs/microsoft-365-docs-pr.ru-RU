---
title: Настройте группу с изоляцией безопасности в среде разработки/тестирования
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Настройте группу с изоляцией безопасности в среде разработки/тестирования...
ms.openlocfilehash: c8d56d3dd6e2c46db6ef1938dee8383b56e8966c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522257"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="a545b-103">Настройте группу с изоляцией безопасности в среде разработки/тестирования</span><span class="sxs-lookup"><span data-stu-id="a545b-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="a545b-104">В этой статье приводятся пошаговые инструкции по созданию [группы с изоляцией безопасности](secure-teams-security-isolation.md) в среде разработки/тестирования.</span><span class="sxs-lookup"><span data-stu-id="a545b-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![Конфигурация для изолированной команды Стратегия компании](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="a545b-106">Используйте эту среду разработки и тестирования, чтобы экспериментировать и настраивать параметры в соответствии с вашими потребностями, прежде чем внедрять этот тип команды в производство.</span><span class="sxs-lookup"><span data-stu-id="a545b-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a545b-107">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="a545b-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a545b-108">Если вы просто хотите тестировать чувствительные и высокочувствительные команды легким способом с минимальными требованиями, следуйте инструкциям в [Облегченной базовой конфигурации](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="a545b-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="a545b-109">Если вы хотите протестировать чувствительные и высокочувствительные команды на моделируемом предприятии, следуйте инструкциям в разделе [Синхронизация хэша паролей](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="a545b-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="a545b-110">Тестирование группы с изолированной защитой не требует имитированной среды корпоративного тестирования, которая включает симулированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a545b-110">Testing an team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a545b-111">Он предоставляется здесь как вариант, чтобы вы могли протестировать группу с изоляцией безопасности и поэкспериментировать с ней в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="a545b-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-group-and-users"></a><span data-ttu-id="a545b-112">Этап 2. Создание и настройка группы и пользователей Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="a545b-112">Phase 2: Create and configure your Azure Active Directory (AD) group and users</span></span>

<span data-ttu-id="a545b-113">На этом этапе вы создаете и настраиваете группу Azure AD и пользователей для вымышленной организации.</span><span class="sxs-lookup"><span data-stu-id="a545b-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>
  
<span data-ttu-id="a545b-114">Сначала создайте группу безопасности на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="a545b-114">First, create a security group with the Azure portal.</span></span>
  
1. <span data-ttu-id="a545b-115">Откройте отдельную вкладку в браузере, а затем перейдите на портал Azure по адресу [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a545b-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="a545b-116">Если необходимо, выполните вход с использованием данных учетной записи глобального администратора для вашей пробной или оплаченной подписки Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a545b-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="a545b-117">На портале Azure выберите **Azure Active Directory > Группы**.</span><span class="sxs-lookup"><span data-stu-id="a545b-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="a545b-118">В колонке **Группы — Все группы** выберите пункт **+ Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="a545b-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="a545b-119">В колонке **Группа**:</span><span class="sxs-lookup"><span data-stu-id="a545b-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="a545b-120">В разделе **Тип группы** выберите **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="a545b-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="a545b-121">Введите **Топ-менеджмент** в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="a545b-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="a545b-122">Выберите **Назначенные** в поле **Тип членства**.</span><span class="sxs-lookup"><span data-stu-id="a545b-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="a545b-123">Нажмите кнопку **Создать**, а затем закройте колонку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="a545b-123">Click **Create**, and then close the **Group** blade.</span></span>
    
<span data-ttu-id="a545b-124">Затем настройте автоматическое лицензирование, чтобы членам новой группы **C-Suite** автоматически назначалась лицензия Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a545b-124">Next, configure automatic licensing so that members of the new **C-Suite** group is automatically assigned a Microsoft 365 E5 license.</span></span>
  
1. <span data-ttu-id="a545b-125">На портале Azure последовательно выберите **Azure Active Directory > Лицензии > Все продукты**.</span><span class="sxs-lookup"><span data-stu-id="a545b-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="a545b-126">В списке выберите **Microsoft 365 корпоративный E5** и щелкните **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="a545b-127">В колонке **Назначение лицензии** щелкните **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="a545b-127">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="a545b-128">В списке групп выберите группу **C-Suite**.</span><span class="sxs-lookup"><span data-stu-id="a545b-128">In the list of groups, select the **C-Suite** group.</span></span>
    
5. <span data-ttu-id="a545b-129">Выберите **Выбрать** > **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-129">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="a545b-130">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="a545b-130">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="a545b-131">Затем [подключитесь к модулю PowerShell для Graph Azure Active Directory](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="a545b-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="a545b-132">Введите имя своей организации, свое местоположение и общий пароль, а затем выполните эти команды из командной строки PowerShell или интегрированной среды сценариев (ISE), чтобы создать новые учетные записи пользователей и добавить их в группу C-Suite:</span><span class="sxs-lookup"><span data-stu-id="a545b-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>
  
```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="a545b-133">Общий пароль используется для автоматизации и упрощения конфигурации среды разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="a545b-133">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="a545b-134">Очевидно, что это не рекомендуется в производственных подписках.</span><span class="sxs-lookup"><span data-stu-id="a545b-134">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="a545b-135">Выполните указанные ниже действия, чтобы убедиться, что лицензирование на основе групп работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="a545b-135">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="a545b-136">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a545b-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="a545b-137">На новой вкладке браузера**Центр администрирования Microsoft 365** щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a545b-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="a545b-138">В списке пользователей выберите **Генеральный директор**.</span><span class="sxs-lookup"><span data-stu-id="a545b-138">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="a545b-139">На панели, в которой перечислены свойства учетной записи пользователя **CEO**, убедитесь, что ей была назначена лицензия **Microsoft 365 корпоративный E5** в **лицензиях на продукт**.</span><span class="sxs-lookup"><span data-stu-id="a545b-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>
    
## <a name="phase-3-create-your-team"></a><span data-ttu-id="a545b-140">Этап 3. Создание вашей группы</span><span class="sxs-lookup"><span data-stu-id="a545b-140">Phase 3: Create your team</span></span>

<span data-ttu-id="a545b-141">На этом этапе вы создаете и настраиваете группу с изоляцией безопасности для членов группы старшего руководства для совместной работы над стратегией компании.</span><span class="sxs-lookup"><span data-stu-id="a545b-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="a545b-142">Во-первых, включите метки чувствительности для защиты содержимого в Microsoft Teams, группах Office 365 и сайтах SharePoint, прежде чем продолжить выполнение действий, описанных в [этой статье](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="a545b-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

<span data-ttu-id="a545b-143">Затем создайте группу.</span><span class="sxs-lookup"><span data-stu-id="a545b-143">Next, create the team:</span></span>

1. <span data-ttu-id="a545b-144">В командах нажмите **Teams** в левой части приложения, затем нажмите **Присоединиться или создать группу** в нижней части списка команд.</span><span class="sxs-lookup"><span data-stu-id="a545b-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="a545b-145">Нажмите **Создать группу** (первая карта, верхний левый угол).</span><span class="sxs-lookup"><span data-stu-id="a545b-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="a545b-146">Выберите **Создать группу с нуля**.</span><span class="sxs-lookup"><span data-stu-id="a545b-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="a545b-147">В списке **Чувствительность** оставьте значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a545b-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="a545b-148">В разделе **Конфиденциальность** нажмите **Приватный**.</span><span class="sxs-lookup"><span data-stu-id="a545b-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="a545b-149">Введите **Стратегия компании**, а затем нажмите **Создать** > **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a545b-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="a545b-150">Далее необходимо настроить метку чувствительности со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="a545b-150">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="a545b-151">Название метки: "Стратегия компании"</span><span class="sxs-lookup"><span data-stu-id="a545b-151">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="a545b-152">Шифрование включено</span><span class="sxs-lookup"><span data-stu-id="a545b-152">Encryption is enabled</span></span>
- <span data-ttu-id="a545b-153">У группы "Стратегия компании" имеются разрешения на совместное редактирование</span><span class="sxs-lookup"><span data-stu-id="a545b-153">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="a545b-154">Выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a545b-154">Follow these steps:</span></span>

1. <span data-ttu-id="a545b-155">Откройте [центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a545b-155">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="a545b-156">В разделе **Решения** нажмите **Защита информации**.</span><span class="sxs-lookup"><span data-stu-id="a545b-156">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="a545b-157">Нажмите **Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="a545b-157">Click **Create a label**.</span></span>
4. <span data-ttu-id="a545b-158">Введите **Стратегия компании** для названия этикетки.</span><span class="sxs-lookup"><span data-stu-id="a545b-158">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="a545b-159">Введите в качестве всплывающей подсказки **документы по стратегии компании старшего руководства** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-159">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="a545b-160">На странице **Шифрование** в раскрывающемся списке **Шифрование** выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-160">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="a545b-161">Чтобы добавить разрешения команды:</span><span class="sxs-lookup"><span data-stu-id="a545b-161">To add the team permissions:</span></span><br>
  <span data-ttu-id="a545b-162">а.</span><span class="sxs-lookup"><span data-stu-id="a545b-162">a.</span></span> <span data-ttu-id="a545b-163">Нажмите кнопку **Назначить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="a545b-163">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="a545b-164">б.</span><span class="sxs-lookup"><span data-stu-id="a545b-164">b.</span></span> <span data-ttu-id="a545b-165">Нажмите **Добавить пользователей или группы**, выберите **Стратегия компании**, а затем нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-165">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="a545b-166">в.</span><span class="sxs-lookup"><span data-stu-id="a545b-166">c.</span></span> <span data-ttu-id="a545b-167">Нажмите кнопку **Выбрать разрешения**.</span><span class="sxs-lookup"><span data-stu-id="a545b-167">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="a545b-168">г.</span><span class="sxs-lookup"><span data-stu-id="a545b-168">d.</span></span> <span data-ttu-id="a545b-169">Выберите **Соавтора** в раскрывающемся списке и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-169">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="a545b-170">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-170">Click **Next**.</span></span>
9. <span data-ttu-id="a545b-171">На странице **Маркировка содержимого** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-171">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="a545b-172">На странице **настроек сайта и группы** установите для **параметров сайта и группы** значение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="a545b-172">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="a545b-173">В раскрывающемся списке **Конфиденциальность сайтов групп, связанных с Office 365**, выберите **Частный - только участники могут получить доступ к сайту**.</span><span class="sxs-lookup"><span data-stu-id="a545b-173">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="a545b-174">В разделе **Неуправляемые устройства** выберите **Блокировать доступ**.</span><span class="sxs-lookup"><span data-stu-id="a545b-174">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="a545b-175">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-175">Click **Next**.</span></span>
14. <span data-ttu-id="a545b-176">На странице **Автоматическая маркировка приложений Office** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-176">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="a545b-177">Нажмите **Отправить**, а затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a545b-177">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="a545b-178">Затем опубликуйте новый ярлык, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a545b-178">Next, publish the new label with these steps:</span></span> 

1. <span data-ttu-id="a545b-179">В Центре соответствия требованиям Microsoft 365 на странице **Защита информации** выберите вкладку **Политики меток**.</span><span class="sxs-lookup"><span data-stu-id="a545b-179">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="a545b-180">Нажмите **Опубликовать ярлыки**.</span><span class="sxs-lookup"><span data-stu-id="a545b-180">Click **Publish labels**.</span></span>
3. <span data-ttu-id="a545b-181">На странице **Выберите метки чувствительности для публикации** нажмите **Выбрать метки чувствительности для публикации**.</span><span class="sxs-lookup"><span data-stu-id="a545b-181">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="a545b-182">Выберите **Стратегию компании** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-182">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="a545b-183">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-183">Click **Next**.</span></span>
6. <span data-ttu-id="a545b-184">На странице **Опубликовать для пользователей и групп** нажмите **Выбрать пользователей и группы**.</span><span class="sxs-lookup"><span data-stu-id="a545b-184">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="a545b-185">Нажмите **Добавить** и выберите **Стратегия компании**.</span><span class="sxs-lookup"><span data-stu-id="a545b-185">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="a545b-186">Нажмите **Добавить**, а затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a545b-186">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="a545b-187">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-187">Click **Next**.</span></span>
10. <span data-ttu-id="a545b-188">На странице параметров политики установите флажок **Пользователи должны предоставить обоснование для удаления метки или метки более низкой классификации**, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-188">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="a545b-189">Введите название **Стратегии компании** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a545b-189">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="a545b-190">Нажмите **Отправить**, а затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a545b-190">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="a545b-191">После того, как ярлык **Стратегия компании** станет доступным после публикации, может пройти некоторое время.</span><span class="sxs-lookup"><span data-stu-id="a545b-191">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="a545b-192">Затем примените свой новый ярлык к команде **Стратегии компании** и обновите тип ссылки для обмена по умолчанию, чтобы уменьшить риск случайного обмена файлами и папками с более широкой аудиторией, чем предполагалось.</span><span class="sxs-lookup"><span data-stu-id="a545b-192">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span> 

1. <span data-ttu-id="a545b-193">Откройте [центр администрирования SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="a545b-193">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="a545b-194">В разделе **Сайты** выберите **Активные сайты**.</span><span class="sxs-lookup"><span data-stu-id="a545b-194">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="a545b-195">Откройте команду **Стратегия компании**.</span><span class="sxs-lookup"><span data-stu-id="a545b-195">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="a545b-196">На вкладке **Политики** под разделом **Чувствительность** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-196">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="a545b-197">Выберите метку **Стратегия компании** и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-197">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="a545b-198">На вкладке **Политики** в разделе **Внешний обмен** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-198">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="a545b-199">**Только пользователи из организации**</span><span class="sxs-lookup"><span data-stu-id="a545b-199">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="a545b-200">В разделе тип ссылки для **Общего доступа по умолчанию** снимите флажок **То же, что и на уровне организации** и выберите **Люди с существующим доступом**.</span><span class="sxs-lookup"><span data-stu-id="a545b-200">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="a545b-201">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-201">Click **Save**.</span></span>

<span data-ttu-id="a545b-202">Затем настройте совместное использование сайта только для владельцев для команды **стратегии компании**.</span><span class="sxs-lookup"><span data-stu-id="a545b-202">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="a545b-203">В командах перейдите на вкладку **Общие** команды **Стратегии компании**.</span><span class="sxs-lookup"><span data-stu-id="a545b-203">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="a545b-204">На панели инструментов для команды щелкните **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="a545b-204">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="a545b-205">Щелкните многоточие, а затем — **Открыть в SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a545b-205">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="a545b-206">На панели инструментов базового сайта SharePoint щелкните значок параметров и выберите вариант **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="a545b-206">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="a545b-207">На панели разрешений сайта в разделе **Общий доступ к сайту** нажмите кнопку **Изменить, как участники могут делиться**.</span><span class="sxs-lookup"><span data-stu-id="a545b-207">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="a545b-208">В разделе **Разрешения на предоставление общего доступа** выберите **Только владельцы сайта могут делиться файлами, папками и сайтом** и щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a545b-208">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="a545b-209">Закройте панели **Разрешения** и **Настройки**.</span><span class="sxs-lookup"><span data-stu-id="a545b-209">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="a545b-210">Если вы войдете в качестве члена группы Стратегии компании, вы увидите **Стратегию компании** в параметре **Чувствительность** на главной панели инструментов Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="a545b-210">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="a545b-211">Выберите метку **Стратегия компании** в параметре **Чувствительность**, чтобы назначить метку файлу.</span><span class="sxs-lookup"><span data-stu-id="a545b-211">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="a545b-212">Ниже приведена итоговая конфигурация для команды "Стратегия компании".</span><span class="sxs-lookup"><span data-stu-id="a545b-212">Here is the resulting configuration for the Company Strategy team.</span></span>

![Конфигурация для изолированной команды Стратегия компании](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="a545b-214">Файлы в команде могут иметь метку чувствительности Стратегии компании, назначенную членами группы Стратегии компании.</span><span class="sxs-lookup"><span data-stu-id="a545b-214">Files in the team can have the Company Strategy sensitivity label assigned by the members of the Company Strategy group.</span></span> <span data-ttu-id="a545b-215">Пример:</span><span class="sxs-lookup"><span data-stu-id="a545b-215">Here is an example.</span></span>

![Пример файла с примененной меткой чувствительности стратегии компании](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config-example.png)
 
## <a name="next-step"></a><span data-ttu-id="a545b-217">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="a545b-217">Next step</span></span>

<span data-ttu-id="a545b-218">Когда вы будете готовы к производственному развертыванию, см. [Настройка группы с изоляцией безопасности](secure-teams-security-isolation.md) для получения подробной информации о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a545b-218">When you are ready for production deployment, see [Configure a team with security isolation](secure-teams-security-isolation.md) for detailed configuration information.</span></span>
