---
title: Защита сайтов SharePoint Online в среде разработки и тестирования
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: Сводка. Создание общедоступных, частных, конфиденциальных и строго конфиденциальных сайтов групп SharePoint Online в среде разработки и тестирования.
ms.openlocfilehash: 6bf18c3d010d7e624666745842f7f3c41176b1b3
ms.sourcegitcommit: 6e01543b3fff50a28719478b19b644991ba7505a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38035699"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a><span data-ttu-id="15d29-103">Защита сайтов SharePoint Online в среде разработки и тестирования</span><span class="sxs-lookup"><span data-stu-id="15d29-103">Secure SharePoint Online sites in a dev/test environment</span></span>

 <span data-ttu-id="15d29-104">**Сводка.** Создание общедоступных, частных, конфиденциальных и строго конфиденциальных сайтов групп SharePoint Online в среде разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="15d29-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in a dev/test environment.</span></span>
  
<span data-ttu-id="15d29-105">Эта статья содержит пошаговые инструкции по созданию среды разработки и тестирования, включающей четыре различных типа сайтов групп SharePoint Online для [решения по защите файлов и сайтов SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="15d29-105">This article provides step-by-step instructions to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) solution.</span></span>
  
![Все четыре сайта группы в безопасной среде разработки и тестирования SharePoint Online.](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
<span data-ttu-id="15d29-107">Используйте это окружение разработки и тестирования для экспериментов с режимами защиты информации и настройкой перед развертыванием сайтов групп SharePoint Online в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="15d29-107">Use this dev/test environment to experiment with the information protection behaviors and fine-tune settings for your specific needs before deploying SharePoint Online team sites in production.</span></span>
  
## <a name="phase-1-create-your-devtest-environment"></a><span data-ttu-id="15d29-108">Этап 1. Создание среды разработки и тестирования</span><span class="sxs-lookup"><span data-stu-id="15d29-108">Phase 1: Create your dev/test environment</span></span>

<span data-ttu-id="15d29-109">На этом этапе вы получите пробные подписки для Office 365 и Enterprise Mobility + Security (EMS) для вымышленной организации.</span><span class="sxs-lookup"><span data-stu-id="15d29-109">In this phase, you obtain trial subscriptions for Office 365 and Enterprise Mobility + Security (EMS) for a fictional organization.</span></span>
  
<span data-ttu-id="15d29-110">Сначала следуйте инструкциям для **этапа 2**, указанного в [разделе о среде разработки и тестирования Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="15d29-110">First, follow the instructions in **Phase 2** of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="15d29-111">Затем оформите пробную подписку на EMS и добавьте ее к той же организации, что и пробную подписку на Office 365.</span><span class="sxs-lookup"><span data-stu-id="15d29-111">Next, sign up for the EMS trial subscription and add it to the same organization as your Office 365 trial subscription.</span></span>
  
1. <span data-ttu-id="15d29-112">При необходимости войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com), используя учетные данные глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="15d29-112">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="15d29-113">В области навигации слева нажмите **Выставление счетов > Приобретение служб**.</span><span class="sxs-lookup"><span data-stu-id="15d29-113">In the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="15d29-p101">На странице **Приобретение служб** найдите элемент **Enterprise Mobility + Security E5**. Наведите на него указатель мыши и выберите **Начать бесплатный пробный период**.</span><span class="sxs-lookup"><span data-stu-id="15d29-p101">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
4. <span data-ttu-id="15d29-116">На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.</span><span class="sxs-lookup"><span data-stu-id="15d29-116">On the **Confirm your order** page, click **Try now**.</span></span>
    
5. <span data-ttu-id="15d29-117">На странице **Получение заказа** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-117">On the **Order receipt** page, click **Continue**.</span></span>
    
<span data-ttu-id="15d29-118">Затем включите лицензию Enterprise Mobility + Security E5 для своей учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="15d29-118">Next, enable the Enterprise Mobility + Security E5 license for your global administrator account.</span></span>
  
1. <span data-ttu-id="15d29-119">Открыв вкладку браузера **Центр администрирования Microsoft 365**, на панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="15d29-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
2. <span data-ttu-id="15d29-120">Выберите свою учетную запись глобального администратора и щелкните ссылку **Изменить** для параметра **Лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="15d29-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
3. <span data-ttu-id="15d29-121">На панели **Лицензии на продукты** переведите переключатель **Enterprise Mobility + Security E5** в положение **Вкл.**, нажмите **Сохранить**, а затем дважды **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="15d29-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="15d29-122">Этап 2. Создание и настройка групп и пользователей Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="15d29-122">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="15d29-123">На этом этапе вы создадите и настроите группы и пользователей Azure AD для вымышленной организации.</span><span class="sxs-lookup"><span data-stu-id="15d29-123">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="15d29-124">Сначала создайте набор групп для обычной организации на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="15d29-124">First, create a set of groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="15d29-p102">Откройте портал Azure ([https://portal.azure.com](https://portal.azure.com)) на отдельной вкладке браузера. Если необходимо, выполните вход, используя данные учетной записи глобального администратора для пробной подписки на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="15d29-p102">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="15d29-127">На портале Azure выберите **Azure Active Directory > Группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-127">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="15d29-128">В колонке **Группы — Все группы** выберите пункт **+ Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="15d29-128">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="15d29-129">В колонке **Группа**:</span><span class="sxs-lookup"><span data-stu-id="15d29-129">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="15d29-130">В разделе **Тип группы** выберите **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="15d29-130">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="15d29-131">Введите **Топ-менеджмент** в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="15d29-131">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="15d29-132">Выберите **Назначенные** в поле **Тип членства**.</span><span class="sxs-lookup"><span data-stu-id="15d29-132">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="15d29-133">Нажмите кнопку **Создать**, а затем закройте колонку **Группа**.</span><span class="sxs-lookup"><span data-stu-id="15d29-133">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="15d29-134">Повторите шаги с 3 по 5 для следующих групп:</span><span class="sxs-lookup"><span data-stu-id="15d29-134">Repeat steps 3-5 for the following group names:</span></span>
    
  - <span data-ttu-id="15d29-135">ИТ-персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-135">IT staff</span></span>
    
  - <span data-ttu-id="15d29-136">Научный персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-136">Research staff</span></span>
    
  - <span data-ttu-id="15d29-137">Штатный персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-137">Regular staff</span></span>
    
  - <span data-ttu-id="15d29-138">Маркетинговый персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-138">Marketing staff</span></span>
    
  - <span data-ttu-id="15d29-139">Торговый персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-139">Sales staff</span></span>
    
7. <span data-ttu-id="15d29-140">Не закрывайте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="15d29-140">Keep the Azure portal tab in your browser open.</span></span>
    
<span data-ttu-id="15d29-141">После этого настройте автоматическое лицензирование, чтобы членам групп автоматически назначались лицензии на подписки Office 365 и EMS.</span><span class="sxs-lookup"><span data-stu-id="15d29-141">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="15d29-142">На портале Azure последовательно выберите **Azure Active Directory > Лицензии > Все продукты**.</span><span class="sxs-lookup"><span data-stu-id="15d29-142">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="15d29-143">В списке выберите **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5** и нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-143">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="15d29-144">В колонке **Назначение лицензии** щелкните **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-144">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="15d29-145">В списке групп выберите следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="15d29-145">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="15d29-146">Топ-менеджмент</span><span class="sxs-lookup"><span data-stu-id="15d29-146">C-Suite</span></span>
    
  - <span data-ttu-id="15d29-147">ИТ-персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-147">IT staff</span></span>
    
  - <span data-ttu-id="15d29-148">Научный персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-148">Research staff</span></span>
    
  - <span data-ttu-id="15d29-149">Штатный персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-149">Regular staff</span></span>
    
  - <span data-ttu-id="15d29-150">Маркетинговый персонал</span><span class="sxs-lookup"><span data-stu-id="15d29-150">Marketing staff</span></span>
    
  - <span data-ttu-id="15d29-151">Сотрудники отдела продаж</span><span class="sxs-lookup"><span data-stu-id="15d29-151">Sales staff</span></span>
    
5. <span data-ttu-id="15d29-152">Выберите **Выбрать** > **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-152">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="15d29-153">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="15d29-153">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="15d29-154">Далее вы [подключитесь к модулю PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="15d29-154">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="15d29-155">Введите название организации, адрес и общий пароль и выполните эти команды в командной строке PowerShell или интегрированной среде сценариев (ISE), чтобы создать учетные записи пользователей и добавить их в свои группы:</span><span class="sxs-lookup"><span data-stu-id="15d29-155">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
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
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="15d29-156">Общий пароль используется для автоматизации и упрощения конфигурации среды разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="15d29-156">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="15d29-157">Очевидно, что это не рекомендуется в производственных подписках.</span><span class="sxs-lookup"><span data-stu-id="15d29-157">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="15d29-158">Выполните указанные ниже действия, чтобы убедиться, что лицензирование на основе групп работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="15d29-158">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="15d29-159">На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="15d29-159">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="15d29-160">На новой вкладке браузера**Центр администрирования Microsoft 365** щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="15d29-160">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="15d29-161">В списке пользователей выберите **Генеральный директор**.</span><span class="sxs-lookup"><span data-stu-id="15d29-161">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="15d29-162">В области, где приведены свойства учетной записи **Генеральный директор**, проверьте, что этой учетной записи назначены лицензии **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5** лицензии (в разделе **Лицензии на продукты**).</span><span class="sxs-lookup"><span data-stu-id="15d29-162">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="15d29-163">Этап 3. Создание меток хранения Office 365</span><span class="sxs-lookup"><span data-stu-id="15d29-163">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="15d29-164">На этом этапе мы создадим метки хранения разных уровней защиты для папок документов на сайтах групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="15d29-164">In this phase, you create the retention labels for the different levels of security for SharePoint Online team site documents folders.</span></span>


1. <span data-ttu-id="15d29-165">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="15d29-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="15d29-166">На вкладке **Главная — соответствие требованиям Microsoft 365** в браузере выберите пункты **Классификации > Метки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-166">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="15d29-167">Щелкните **Метки хранения > Создать метку**.</span><span class="sxs-lookup"><span data-stu-id="15d29-167">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="15d29-168">В области **Назовите метку** введите **Внутренний общедоступный** в поле **Название**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-168">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="15d29-169">В области **Дескрипторы плана файлов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-169">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="15d29-170">В области **Параметры метки** при необходимости установите параметр **Хранение** в положение **Вкл.** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-170">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="15d29-171">В области **Проверьте параметры** нажмите кнопку **Создать эту метку**.</span><span class="sxs-lookup"><span data-stu-id="15d29-171">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="15d29-172">Повторите шаги 3–7 для дополнительных меток с этими именами:</span><span class="sxs-lookup"><span data-stu-id="15d29-172">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="15d29-173">частные</span><span class="sxs-lookup"><span data-stu-id="15d29-173">Private</span></span>
    
  - <span data-ttu-id="15d29-174">Конфиденциальный</span><span class="sxs-lookup"><span data-stu-id="15d29-174">Sensitive</span></span>
    
  - <span data-ttu-id="15d29-175">Строго конфиденциально</span><span class="sxs-lookup"><span data-stu-id="15d29-175">Highly Confidential</span></span>
  
9. <span data-ttu-id="15d29-176">В области **Главная > Метки** щелкните **Опубликовать метки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-176">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="15d29-177">В области **Выберите метки для публикации** щелкните **Выберите метки для публикации**.</span><span class="sxs-lookup"><span data-stu-id="15d29-177">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="15d29-178">В области **Выбор меток** нажмите кнопку **Добавить** и выберите все четыре метки.</span><span class="sxs-lookup"><span data-stu-id="15d29-178">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="15d29-179">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-179">Click **Done**.</span></span>
    
13. <span data-ttu-id="15d29-180">В области **Выберите метки для публикации** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-180">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="15d29-181">В области **Выберите расположения** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-181">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="15d29-182">В области **Укажите имя для политики** введите **Пример организации** в поле **Имя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-182">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="15d29-183">В области **Проверьте параметры** последовательно нажмите кнопки **Опубликовать метки** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="15d29-183">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="15d29-184">Этап 4. Создание сайтов групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="15d29-184">Phase 4: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="15d29-185">На этом этапе вы создадите и настроите четыре типа сайтов групп SharePoint Online для примера организации.</span><span class="sxs-lookup"><span data-stu-id="15d29-185">In this phase, you create and configure the four types of SharePoint Online team sites for your example organization.</span></span>
  
### <a name="organization-wide-team-site"></a><span data-ttu-id="15d29-186">Сайт группы "Для всей организации"</span><span class="sxs-lookup"><span data-stu-id="15d29-186">Organization wide team site</span></span>

<span data-ttu-id="15d29-187">Чтобы создать общедоступный сайт группы SharePoint Online с базовым уровнем защиты, выполните приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="15d29-187">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="15d29-188">Если необходимо, войдите на [портал Office 365](https://portal.office.com) с использованием учетных данных глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="15d29-188">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="15d29-189">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15d29-189">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="15d29-190">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="15d29-190">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="15d29-191">На странице **Создание сайта** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-191">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="15d29-192">В поле **Имя сайта** введите **Для всей организации**.</span><span class="sxs-lookup"><span data-stu-id="15d29-192">In **Site name**, type **Organization wide**.</span></span> 
    
6. <span data-ttu-id="15d29-193">В поле **Описание сайта группы** введите **Сайт SharePoint для всей организации**.</span><span class="sxs-lookup"><span data-stu-id="15d29-193">In **Team site description**, type **SharePoint site for the entire organization**.</span></span>
    
7. <span data-ttu-id="15d29-194">В разделе **Параметры конфиденциальности** выберите **Общедоступная группа: все в организации имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-194">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="15d29-195">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-195">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="15d29-196">Далее настройте папку документов сайта группы "Для всей организации" для метки "Внутренний общедоступный".</span><span class="sxs-lookup"><span data-stu-id="15d29-196">Next, configure the documents folder of the Organization wide team site for the Internal Public label.</span></span>
  
1. <span data-ttu-id="15d29-197">На вкладке браузера **Для всей организации — главная** щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-197">In the **Organization wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="15d29-198">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-198">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="15d29-199">В разделе **Разрешения и управление** нажмите **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="15d29-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="15d29-200">В разделе **Параметры — применение метки** выберите метку **Внутренний общедоступный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-200">In **Settings-Apply Label**, select **Internal Public**, and then click **Save**.</span></span>
    
### <a name="project-1-team-site"></a><span data-ttu-id="15d29-201">Сайт группы "Проект 1"</span><span class="sxs-lookup"><span data-stu-id="15d29-201">Project 1 team site</span></span>

<span data-ttu-id="15d29-202">Чтобы создать частный сайт группы SharePoint Online с базовым уровнем защиты для проекта в организации, выполните приведенные далее действия.</span><span class="sxs-lookup"><span data-stu-id="15d29-202">To create a baseline private SharePoint Online team site for a project within the organization, do the following:</span></span>
  
1. <span data-ttu-id="15d29-203">Если необходимо, войдите на [портал Office 365](https://portal.office.com) с использованием учетных данных глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="15d29-203">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="15d29-204">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15d29-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="15d29-205">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="15d29-205">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="15d29-206">На странице **Создание сайта** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-206">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="15d29-207">В поле **Имя сайта** введите **Проект 1**.</span><span class="sxs-lookup"><span data-stu-id="15d29-207">In **Site name**, type **Project 1**.</span></span> 
    
6. <span data-ttu-id="15d29-208">В поле **Описание сайта группы** введите **Сайт SharePoint для проекта 1**.</span><span class="sxs-lookup"><span data-stu-id="15d29-208">In **Team site description,** type **SharePoint site for Project 1**.</span></span>
    
7. <span data-ttu-id="15d29-209">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-209">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="15d29-210">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-210">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="15d29-211">Далее настройте папку документов сайта группы "Проект 1" для метки "Частный".</span><span class="sxs-lookup"><span data-stu-id="15d29-211">Next, configure the documents folder of the Project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="15d29-212">На вкладке браузера **Проект 1 — главная** щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-212">In the **Project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="15d29-213">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-213">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="15d29-214">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="15d29-214">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="15d29-215">В разделе **Параметры — применение метки** выберите метку **Частный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-215">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="marketing-campaigns-team-site"></a><span data-ttu-id="15d29-216">Сайт группы маркетинговых кампаний</span><span class="sxs-lookup"><span data-stu-id="15d29-216">Marketing campaigns team site</span></span>

<span data-ttu-id="15d29-217">Чтобы создать изолированный сайт группы SharePoint Online с конфиденциальным уровнем защиты для участников маркетинговых кампаний, выполните приведенные далее действия.</span><span class="sxs-lookup"><span data-stu-id="15d29-217">To create a sensitive-level isolated SharePoint Online team site for marketing campaign resources, do the following:</span></span>

 
1. <span data-ttu-id="15d29-218">Если необходимо, войдите на [портал Office 365](https://portal.office.com) с использованием учетных данных глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="15d29-218">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="15d29-219">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15d29-219">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="15d29-220">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="15d29-220">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="15d29-221">На странице **Создание сайта** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-221">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="15d29-222">В поле **Имя сайта группы** введите **Маркетинговые кампании**.</span><span class="sxs-lookup"><span data-stu-id="15d29-222">In **Team site name**, type **Marketing campaigns**.</span></span>
    
6. <span data-ttu-id="15d29-223">В поле **Описание сайта группы** введите **Сайт SharePoint для участников маркетинговых кампаний (конфиденциальный)**.</span><span class="sxs-lookup"><span data-stu-id="15d29-223">In **Team site description**, type **SharePoint site for marketing campaign resources (sensitive)**.</span></span>
    
7.  <span data-ttu-id="15d29-224">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-224">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="15d29-225">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-225">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="15d29-226">Перейдите к новой вкладке **Маркетинговые кампании** в браузере, а затем на панели инструментов нажмите значок параметров и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="15d29-226">On the new **Marketing campaigns** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="15d29-227">В области **Разрешения для сайта** щелкните **Параметры дополнительных разрешений**.</span><span class="sxs-lookup"><span data-stu-id="15d29-227">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="15d29-228">На новой вкладке браузера **Разрешения** щелкните **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="15d29-228">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="15d29-229">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить участникам приглашать других пользователей в группу участников сайта**, введите **ITAdmin1@**\<название_организации>**.onmicrosoft.com** в поле **Отправлять все запросы на доступ по следующему адресу электронной почты**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-229">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="15d29-230">В списке выберите пункт **Маркетинговые кампании — участники**.</span><span class="sxs-lookup"><span data-stu-id="15d29-230">Click **Marketing campaigns Members** in the list.</span></span>
    
14. <span data-ttu-id="15d29-231">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="15d29-231">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="15d29-232">В диалоговом окне **Общий доступ** введите **Сотрудники отдела маркетинга**, выберите эту группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="15d29-232">In the **Share** dialog box, type **Marketing staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="15d29-233">Повторите этапы 14 и 15 для учетной записи пользователя **Исследователь1**.</span><span class="sxs-lookup"><span data-stu-id="15d29-233">Repeat steps 14 and 15 for the **Researcher1** user account.</span></span>
    
17. <span data-ttu-id="15d29-234">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="15d29-234">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="15d29-235">Выберите в списке пункт **Маркетинговые кампании — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-235">Click **Marketing campaigns Owners** in the list.</span></span>
    
19. <span data-ttu-id="15d29-236">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="15d29-236">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="15d29-237">В диалоговом окне **Общий доступ** введите **ИТ-персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="15d29-237">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="15d29-238">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="15d29-238">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="15d29-239">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Маркетинговые кампании — главная** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="15d29-239">Close the **People and Groups** tab in your browser, click the **Marketing campaigns-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="15d29-240">Ниже представлены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="15d29-240">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="15d29-241">Группа SharePoint **Маркетинговые кампании — участники** содержит только группу **Маркетинговые кампании** (в которой находится учетная запись глобального администратора), группу **Маркетинговый персонал** (в которой находятся учетные записи пользователей Marketing1 и Marketing2) и учетную запись пользователя **Researcher1**.</span><span class="sxs-lookup"><span data-stu-id="15d29-241">The **Marketing campaigns-Members** SharePoint group contains only the **Marketing campaigns** group (which contains the global administrator user account), the **Marketing staff** group (which contains the Marketing1 and Marketing2 user accounts), and the **Researcher1** user account.</span></span>
    
- <span data-ttu-id="15d29-242">Группа SharePoint **Маркетинговые кампании — владельцы** содержит только группу **ИТ-персонал** (в которой находятся только учетные записи пользователей ITAdmin1 и ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="15d29-242">The **Marketing campaigns-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="15d29-243">Группа SharePoint **Маркетинговые кампании — посетители** не содержит групп или учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="15d29-243">The **Marketing campaigns-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="15d29-244">Участники не могут изменять разрешения уровня веб-сайта (это могут делать только члены группы **Маркетинговые кампании — владельцы**).</span><span class="sxs-lookup"><span data-stu-id="15d29-244">Members cannot modify site-level permissions (this can only be done by members of the **Marketing campaigns-Owners** group).</span></span>
    
- <span data-ttu-id="15d29-245">У других учетных записей нет доступа к сайту и его ресурсам, но они могут запрашивать доступ к сайту. При этом в почтовый ящик пользователя "ИТ-администратор1" отправляется электронное сообщение.</span><span class="sxs-lookup"><span data-stu-id="15d29-245">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="15d29-246">Теперь настройте папку документов на сайте группы "Маркетинговые кампании" на использование метки "Конфиденциальный".</span><span class="sxs-lookup"><span data-stu-id="15d29-246">Next, configure the documents folder of the Marketing campaigns team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="15d29-247">На вкладке браузера **Маркетинговые кампании — главная** щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-247">In the **Marketing campaigns-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="15d29-248">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-248">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="15d29-249">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="15d29-249">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="15d29-250">В разделе **Параметры — применение метки** выберите метку **Конфиденциальный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-250">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="15d29-251">Настройте политику защиты от потери данных (DLP), которая уведомляет пользователей, когда они предоставляют общий доступ к документу на сайте группы SharePoint Online с меткой "Конфиденциальный" (в число таких сайтов входит сайт "Маркетинговые кампании") за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="15d29-251">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label, which includes the Marketing campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="15d29-252">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="15d29-252">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="15d29-253">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="15d29-253">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="15d29-254">В области **Главная > Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="15d29-254">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="15d29-255">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-255">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="15d29-256">В области **Назовите политику** введите **Сайты групп SharePoint Online с меткой "Конфиденциальный"** в поле **Имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-256">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="15d29-257">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-257">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="15d29-258">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-258">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="15d29-259">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-259">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="15d29-260">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="15d29-260">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="15d29-261">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-261">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="15d29-262">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-262">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="15d29-263">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-263">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="15d29-264">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="15d29-264">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="15d29-265">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="15d29-265">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="15d29-266">В текстовом поле введите или вставьте одну из следующих подсказок в зависимости от того, применена ли служба Azure Information Protection, чтобы защитить строго конфиденциальные файлы:</span><span class="sxs-lookup"><span data-stu-id="15d29-266">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="15d29-p104">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="15d29-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="15d29-270">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-270">Click **OK**.</span></span>
    
17. <span data-ttu-id="15d29-271">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-271">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="15d29-272">В области **Вы хотите включить политику или сначала проверить, как все работает?** выберите пункт **Да, включить сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-272">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="15d29-273">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="15d29-273">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="15d29-274">Сайт группы "Стратегия организации"</span><span class="sxs-lookup"><span data-stu-id="15d29-274">Company strategy team site</span></span>

<span data-ttu-id="15d29-275">Чтобы создать изолированный сайт группы SharePoint Online со строго конфиденциальным уровнем защиты для стратегических ресурсов организации, включающих высшее руководство, выполните приведенные далее действия.</span><span class="sxs-lookup"><span data-stu-id="15d29-275">To create an isolated SharePoint Online team site at the highly confidential level for strategic company resources of the chief executives of the organization, do the following:</span></span>
  
1. <span data-ttu-id="15d29-276">Если необходимо, войдите на [портал Office 365](https://portal.office.com) с использованием учетных данных глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="15d29-276">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="15d29-277">В списке плиток выберите **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="15d29-277">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="15d29-278">На новой вкладке **SharePoint** в браузере щелкните **+ Создать сайт**.</span><span class="sxs-lookup"><span data-stu-id="15d29-278">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="15d29-279">На странице **Создание сайта** щелкните **Сайт группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-279">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="15d29-280">В поле **Имя сайта группы** введите **Стратегия организации**.</span><span class="sxs-lookup"><span data-stu-id="15d29-280">In **Team site name**, type **Company strategy**.</span></span>
    
6. <span data-ttu-id="15d29-281">В поле **Описание сайта группы** введите **Сайт SharePoint для стратегии организации (строго конфиденциальный)**.</span><span class="sxs-lookup"><span data-stu-id="15d29-281">In **Team site description**, type **SharePoint site for company strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="15d29-282">В разделе **Параметры конфиденциальности** выберите **Закрытая группа: только участники имеют доступ к этому сайту** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-282">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="15d29-283">В области **Кого вы хотите добавить?** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-283">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="15d29-284">В новой вкладке **Стратегия организации** в браузере нажмите значок параметров на панели инструментов и выберите **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="15d29-284">On the new **Company strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="15d29-285">В области **Разрешения для сайта** щелкните **Параметры дополнительных разрешений**.</span><span class="sxs-lookup"><span data-stu-id="15d29-285">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="15d29-286">На новой вкладке браузера **Разрешения** щелкните **Параметры запросов на доступ**.</span><span class="sxs-lookup"><span data-stu-id="15d29-286">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="15d29-287">В диалоговом окне **Параметры запросов на доступ** снимите флажки **Разрешить участникам совместный доступ к этому сайту, а также отдельным файлам и папкам** и **Разрешить участникам приглашать других пользователей в группу участников сайта** (все три флажка должны быть сняты) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-287">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="15d29-288">Выберите в списке пункт **Стратегия организации — участники**.</span><span class="sxs-lookup"><span data-stu-id="15d29-288">Click **Company strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="15d29-289">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="15d29-289">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="15d29-290">В диалоговом окне **Общий доступ** введите **Топ-менеджмент**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="15d29-290">In the **Share** dialog box, type **C-Suite**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="15d29-291">Выберите в списке пункт **Стратегия организации — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-291">Click **Company strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="15d29-292">На странице **Пользователи и группы** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="15d29-292">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="15d29-293">В диалоговом окне **Общий доступ** введите **ИТ-персонал**, выберите группу и нажмите **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="15d29-293">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="15d29-294">Нажмите кнопку "Назад" в браузере.</span><span class="sxs-lookup"><span data-stu-id="15d29-294">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="15d29-295">Закройте вкладку **Пользователи и группы** в браузере, перейдите на вкладку **Стратегия организации — главная** в браузере и закройте область **Разрешения для сайта**.</span><span class="sxs-lookup"><span data-stu-id="15d29-295">Close the **People and Groups** tab in your browser, click the **Company strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="15d29-296">Ниже приведены результаты настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="15d29-296">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="15d29-297">Группа SharePoint **Стратегия организации — участники** содержит только группу **Топ-менеджмент** (в которую входят только учетные записи генерального директора, финансового директора и директора по информационным технологиям) и группу **Стратегия организации** (в которую входит только учетная запись глобального администратора).</span><span class="sxs-lookup"><span data-stu-id="15d29-297">The **Company strategy-Members** SharePoint group contains only the **C-Suite** group (which contains only the CEO, CFO, and CIO user accounts) and the **Company strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="15d29-298">Группа SharePoint **Стратегия организации — владельцы** содержит только группу **ИТ-персонал** (в которой находятся только учетные записи пользователей "ITAdmin1" и "ITAdmin2").</span><span class="sxs-lookup"><span data-stu-id="15d29-298">The **Company strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="15d29-299">Группа SharePoint **Стратегия организации — посетители** не содержит групп или учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="15d29-299">The **Company strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="15d29-300">Участники не могут изменять разрешения уровня веб-сайта (это могут делать только члены группы **Стратегия организации — владельцы**).</span><span class="sxs-lookup"><span data-stu-id="15d29-300">Members cannot modify site-level permissions (this can only be done by members of the **Company strategy-Owners** group).</span></span>
    
- <span data-ttu-id="15d29-p105">Другие учетные записи пользователей не могут получить доступ к сайту или его ресурсам или запросить доступ к сайту. Дополнительные разрешения для сайта должен назначить глобальный администратор или участник группы **Стратегия организации — владельцы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Company strategy-Owners** group.</span></span>
    
<span data-ttu-id="15d29-303">Затем настройте папку документов на сайте стратегической группы компании на использование метки "Строго конфиденциально".</span><span class="sxs-lookup"><span data-stu-id="15d29-303">Next, configure the documents folder of the Company strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="15d29-304">На вкладке браузера **Стратегия организации — главная** щелкните **Документы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-304">In the **Company strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="15d29-305">Щелкните значок параметров и выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-305">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="15d29-306">В разделе **Разрешения и управление** нажмите кнопку **Применить метку к элементам в этой библиотеке**.</span><span class="sxs-lookup"><span data-stu-id="15d29-306">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="15d29-307">В разделе **Параметры — применение метки** выберите метку **Строго конфиденциальный** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-307">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="15d29-308">Настройте политику защиты от потери данных (DLP), которая блокирует пользователей, когда они предоставляют общий доступ к документу на сайте группы SharePoint Online с меткой "Строго конфиденциальный" (в число таких сайтов входит сайт "Стратегия организации") за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="15d29-308">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label, which includes the Company strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="15d29-309">Войдите на [портал соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) с использованием данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="15d29-309">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="15d29-310">На новой вкладке **Соответствие требованиям Microsoft 365** в браузере выберите пункты **Политики > Защита от потери данных**.</span><span class="sxs-lookup"><span data-stu-id="15d29-310">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="15d29-311">В области **Главная > Защита от потери данных** нажмите кнопку **Создание политики**.</span><span class="sxs-lookup"><span data-stu-id="15d29-311">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="15d29-312">В области **Начать с шаблона или создать настраиваемую политику** выберите **Настраиваемая**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-312">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="15d29-313">В области **Назовите политику** введите **Сайты групп SharePoint Online с меткой "Строго конфиденциальный"** в поле **Имя**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-313">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="15d29-314">В области **Выберите расположения** щелкните **Позволить мне выбрать расположения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-314">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="15d29-315">В списке расположений отключите параметры **Электронная почта Exchange**, **Учетные записи OneDrive** и **Сообщения из чатов и каналов Teams**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-315">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="15d29-316">В области **Выберите тип содержимого, которое вы хотите защитить** щелкните ссылку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-316">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="15d29-317">В области **Выбрать типы содержимого для защиты** выберите **Добавить** в раскрывающемся списке, а затем выберите **Метки хранения**.</span><span class="sxs-lookup"><span data-stu-id="15d29-317">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="15d29-318">В области **Метки хранения** нажмите кнопку **Добавить**, укажите метку **Строго конфиденциальный** и последовательно нажмите кнопки **Добавить** > **Готово**.</span><span class="sxs-lookup"><span data-stu-id="15d29-318">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="15d29-319">В области **Выбрать типы содержимого для защиты** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-319">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="15d29-320">В области **Выберите тип содержимого, которое вы хотите защитить** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-320">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="15d29-321">В области **Что необходимо делать, если мы обнаружим конфиденциальные сведения?** щелкните **Настройка подсказки и уведомления**.</span><span class="sxs-lookup"><span data-stu-id="15d29-321">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="15d29-322">В области **Настройка подсказок политики и уведомлений по электронной почте** щелкните **Измените текст подсказки политики**.</span><span class="sxs-lookup"><span data-stu-id="15d29-322">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="15d29-323">В текстовом поле введите или вставьте одну из следующих подсказок в зависимости от того, применена ли служба Azure Information Protection, чтобы защитить строго конфиденциальные файлы:</span><span class="sxs-lookup"><span data-stu-id="15d29-323">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="15d29-p106">Чтобы предоставить доступ пользователю за пределами организации, скачайте файл и откройте его. Выберите пункты "Файл > Защитить документ > Зашифровать паролем", а затем укажите надежный пароль. Отправьте пароль в отдельном сообщении или с помощью других средств связи.</span><span class="sxs-lookup"><span data-stu-id="15d29-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="15d29-327">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-327">Click **OK**.</span></span>
    
17. <span data-ttu-id="15d29-328">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-328">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="15d29-329">В области **Включить политику или сначала протестировать ее?** выберите пункт **Да, включить ее сразу**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="15d29-329">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="15d29-330">В области **Проверка параметров** нажмите **Создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="15d29-330">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
   
    
<span data-ttu-id="15d29-331">Далее выполните инструкции в статье [Активация Azure RMS с помощью Центра администрирования Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="15d29-331">Next, follow the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="15d29-332">Затем настройте для Azure Information Protection новую политику области и вложенную метку для группы "Топ-менеджмент" для защиты и разрешений, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="15d29-332">Next, configure Azure Information Protection with a new policy and sub-label scoped for the C-Suite group for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="15d29-333">При необходимости войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="15d29-333">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="15d29-334">Перейдите на портал Azure ([https://portal.azure.com](https://portal.azure.com)), открыв отдельную вкладку браузера.</span><span class="sxs-lookup"><span data-stu-id="15d29-334">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="15d29-335">Если вы настраиваете Azure Information Protection впервые, ознакомьтесь с этими [инструкциями](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span><span class="sxs-lookup"><span data-stu-id="15d29-335">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>
    
4. <span data-ttu-id="15d29-336">На панели списка выберите **Все службы**, введите **information**, а затем выберите **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="15d29-336">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="15d29-337">Выберите **Метки**.</span><span class="sxs-lookup"><span data-stu-id="15d29-337">Click **Labels**.</span></span>
    
6. <span data-ttu-id="15d29-338">Щелкните правой кнопкой мыши метку **Строго конфиденциально** и выберите элемент **Добавить подчин. метку**.</span><span class="sxs-lookup"><span data-stu-id="15d29-338">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="15d29-339">Введите **Представители топ-менеджмента** в полях **Имя** и **Описание**.</span><span class="sxs-lookup"><span data-stu-id="15d29-339">Type **C-Suite members** in **Name** and **Description**.</span></span>
    
8. <span data-ttu-id="15d29-340">В разделе **Задайте разрешения для документов и электронных писем, имеющих эту метку** нажмите кнопку **Защитить**.</span><span class="sxs-lookup"><span data-stu-id="15d29-340">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="15d29-341">В разделе **Защита** выберите элемент **Azure (облачный ключ)**.</span><span class="sxs-lookup"><span data-stu-id="15d29-341">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="15d29-342">В колонке **Защита** в разделе **Параметры защиты** нажмите кнопку **+ Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="15d29-342">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="15d29-343">Перейдите к колонке **Добавление разрешений** и выберите **+ Обзор каталога** в разделе **Укажите пользователей и группы**.</span><span class="sxs-lookup"><span data-stu-id="15d29-343">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="15d29-344">В области **Пользователи и группы AAD** выберите группу **Топ-менеджмент** и нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="15d29-344">On the **AAD Users and Groups** pane, select **C-Suite**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="15d29-345">В разделе **Выбрать из предустановленных разрешений или задать пользовательские** выберите вариант **Пользовательские**, а затем установите флажки **Просмотреть права**, **Изменить контент**, **Сохранить**, **Ответить** и **Ответить всем**.</span><span class="sxs-lookup"><span data-stu-id="15d29-345">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="15d29-346">Дважды нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-346">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="15d29-347">В колонке **Подчиненная метка** нажмите кнопку **Сохранить**, а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-347">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="15d29-348">В колонке **Azure Information Protection** щелкните элементы **Политики > + Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="15d29-348">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="15d29-349">Введите **CompanyStrategy** в поле **Имя политики** и **Документы на сайте группы стратегии организации** в поле **Описание**.</span><span class="sxs-lookup"><span data-stu-id="15d29-349">Type **CompanyStrategy** in **Policy name** and **Documents in the Company strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="15d29-350">Щелкните пункты **Выберите, к каким пользователям или группам будет применяться эта политика > Пользователи или группы**, а затем выберите **Топ-менеджмент**.</span><span class="sxs-lookup"><span data-stu-id="15d29-350">Click **Select which users or groups get this policy > User/Groups**, and then select **C-Suite**.</span></span>
    
19. <span data-ttu-id="15d29-351">Щелкните **Выбрать > ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-351">Click **Select > OK**.</span></span>

20. <span data-ttu-id="15d29-p107">Выберите элемент **Добавить или удалить метки**. В панели **Политики: добавление и удаление меток** нажмите **Топ-менеджмент**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-p107">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **C-Suite**, and then click **OK**.</span></span>   

21. <span data-ttu-id="15d29-354">Нажмите кнопку **Сохранить**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15d29-354">Click **Save**, and then click **OK**.</span></span>
    
<span data-ttu-id="15d29-355">Чтобы защитить документ с помощью Azure Information Protection и новой метки, необходимо [установить клиент Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) на тестовом компьютере, установить Office из Центра администрирования и затем выполнить вход из Microsoft Word с помощью учетной записи в группе **Топ-менеджмент** пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="15d29-355">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **C-Suite** group of your trial subscription.</span></span>
  
<span data-ttu-id="15d29-356">Теперь вы готовы к созданию документов на этих четырех сайтах и тестированию доступа к ним с помощью различных учетных записей пользователей в пробной подписке.</span><span class="sxs-lookup"><span data-stu-id="15d29-356">You are now ready to create documents in these four sites and test access to them with various user accounts in your trial subscription.</span></span>
  
<span data-ttu-id="15d29-357">Здесь приведена общая конфигурация для всех четырех сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="15d29-357">Here is the overall configuration for all four SharePoint Online team sites.</span></span>
  
![Все четыре сайта группы в безопасной среде разработки и тестирования SharePoint Online.](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a><span data-ttu-id="15d29-359">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="15d29-359">Next step</span></span>

<span data-ttu-id="15d29-360">Когда вы будете готовы к выполнению рабочего развертывания безопасных сайтов SharePoint Online, прочтите статью [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) (Защита сайтов и файлов SharePoint Online), содержащую подробные сведения и ссылки на статьи с пошаговыми руководствами.</span><span class="sxs-lookup"><span data-stu-id="15d29-360">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15d29-361">См. также</span><span class="sxs-lookup"><span data-stu-id="15d29-361">See Also</span></span>

[<span data-ttu-id="15d29-362">Безопасность сайтов и файлов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="15d29-362">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="15d29-363">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="15d29-363">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="15d29-364">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="15d29-364">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




