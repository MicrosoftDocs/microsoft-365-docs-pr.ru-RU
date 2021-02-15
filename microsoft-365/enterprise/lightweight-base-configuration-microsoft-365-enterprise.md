---
title: Простая базовая конфигурация
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Используйте это руководство по лаборатории тестирования для создания облегченной тестовой среды для тестирования Microsoft 365 для предприятий.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487392"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="a091a-103">Простая базовая конфигурация</span><span class="sxs-lookup"><span data-stu-id="a091a-103">The lightweight base configuration</span></span>

<span data-ttu-id="a091a-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="a091a-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a091a-105">В этой статье описывается создание упрощенной среды с подпиской Microsoft 365 E5 и компьютером под управлением Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="a091a-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="a091a-107">Создание облегченной тестовой среды состоит из пяти этапов:</span><span class="sxs-lookup"><span data-stu-id="a091a-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="a091a-108">Этап 1. Создание подписки на Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a091a-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="a091a-109">Этап 2. Настройка пробной подписки на Office 365</span><span class="sxs-lookup"><span data-stu-id="a091a-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="a091a-110">Этап 3. Добавление пробной подписки Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a091a-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="a091a-111">Этап 4. Создание компьютера с ОС Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="a091a-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="a091a-112">Этап 5. Присоединение компьютера с Windows 10 к Azure AD</span><span class="sxs-lookup"><span data-stu-id="a091a-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="a091a-113">Используйте итоговую среду для тестирования функций и функций [Microsoft 365 для предприятий.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="a091a-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="a091a-115">Visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="a091a-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="a091a-116">Можно напечатать эту статью, чтобы записать информацию, которая понадобится вам для этой среды в течение 30 дней пробной подписки на Office 365.</span><span class="sxs-lookup"><span data-stu-id="a091a-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="a091a-117">Пробную подписку можно легко продлить еще на 30 дней.</span><span class="sxs-lookup"><span data-stu-id="a091a-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="a091a-118">Чтобы создать постоянную среду тестирования, создайте новую платную подписку с отдельным клиентом Azure AD и с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="a091a-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="a091a-119">Этап 1. Создание подписки на Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a091a-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="a091a-120">Начнем с пробной подписки Microsoft 365 E5, а затем добавим в нее подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="a091a-121">Рекомендуется создать пробную подписку на Office 365, чтобы в тестовой среде был отдельный клиент Azure AD от всех платных подписок, которые у вас есть в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="a091a-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="a091a-122">Это разделение означает, что вы можете добавлять и удалять пользователей и группы в тестовом клиенте, не затрагивая производственные подписки.</span><span class="sxs-lookup"><span data-stu-id="a091a-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="a091a-123">Чтобы оформить пробную подписку Microsoft 365 E5, потребуется вымышленное название компании и новая учетная запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a091a-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="a091a-p103">Рекомендуем использовать в качестве названия компании какую-нибудь вариацию имени Contoso (вымышленной компании, используемой в примерах от Майкрософт), но это необязательно. Запишите здесь название своей вымышленной компании:</span><span class="sxs-lookup"><span data-stu-id="a091a-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![Линия](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="a091a-p104">Чтобы зарегистрировать новую учетную запись Майкрософт, перейдите на сайт [https://outlook.com](https://outlook.com) и создайте учетную запись, используя новый адрес электронной почты. Эта учетная запись будет использоваться для регистрации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a091a-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="a091a-129">Запишите здесь имя и фамилию для новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="a091a-129">Record the first and last name of your new account here:</span></span> ![Линия](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="a091a-131">Запишите здесь адрес электронной почты новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="a091a-131">Record the new email account address here:</span></span> ![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="a091a-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="a091a-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="a091a-134">Оформление пробной подписки на Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="a091a-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="a091a-135">В браузере перейдите к [https://aka.ms/e5trial](https://aka.ms/e5trial) .</span><span class="sxs-lookup"><span data-stu-id="a091a-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="a091a-136">На шаге 1 страницы "Благодарим вас за выбор **Office 365 E5"** введите новый адрес учетной записи электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a091a-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="a091a-137">На шаге 2 процесса подписки введите запрашиваемую информацию и выполните проверку.</span><span class="sxs-lookup"><span data-stu-id="a091a-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="a091a-138">В шаге 3 введите название организации, а затем имя учетной записи, которая будет глобальным администратором подписки.</span><span class="sxs-lookup"><span data-stu-id="a091a-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="a091a-139">Запишите сведения страницы входа (выделите и скопируйте) с шага 4 здесь:</span><span class="sxs-lookup"><span data-stu-id="a091a-139">For step 4, record the sign-in page here (select and copy):</span></span> ![Линия](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="a091a-141">Запишите здесь идентификатор пользователя: ![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a091a-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="a091a-142">Зафиксировать пароль, который вы ввели в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="a091a-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="a091a-143">Это значение будет называться **именем глобального администратора**.</span><span class="sxs-lookup"><span data-stu-id="a091a-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="a091a-144">Выберите **"Перейти к установке"**.</span><span class="sxs-lookup"><span data-stu-id="a091a-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="a091a-145">In Office 365 E5 Setup, select **Continue using your *organization*.onmicrosoft.com for email and signing in,** and then select **Exit and continue later**.</span><span class="sxs-lookup"><span data-stu-id="a091a-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="a091a-146">Должен открыться Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a091a-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="a091a-147">Этап 2. Настройка пробной подписки на Office 365</span><span class="sxs-lookup"><span data-stu-id="a091a-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="a091a-148">На этом этапе настраивается подписка с дополнительными пользователями, этим пользователям назначаются лицензии Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="a091a-149">Чтобы подключиться к подписке с помощью модуля Azure Active Directory PowerShell для Graph с компьютера, воспользуйтесь инструкциями в этой теме, чтобы подключиться к [Microsoft 365 с помощью PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="a091a-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="a091a-150">В **диалоговом Windows PowerShell запроса** учетных данных введите имя глобального администратора (например, *jdoe@contosotoycompany.onmicrosoft.com)* и пароль.</span><span class="sxs-lookup"><span data-stu-id="a091a-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="a091a-151">Заполните название организации (например, *contosotoycompany),* двух символьный код страны для расположения, общий пароль учетной записи, а затем запустите следующие команды в командной записи PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a091a-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="a091a-152">Общий пароль используется для автоматизации и упрощения конфигурации среды тестирования.</span><span class="sxs-lookup"><span data-stu-id="a091a-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="a091a-153">Очевидно, что это не рекомендуется в производственных подписках.</span><span class="sxs-lookup"><span data-stu-id="a091a-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="a091a-154">Запишите важнейшую информацию для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="a091a-154">Record key information for future reference</span></span>

<span data-ttu-id="a091a-155">Если эти значения еще не записаны, зафиксировать их теперь:</span><span class="sxs-lookup"><span data-stu-id="a091a-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="a091a-156">Имя глобального администратора:</span><span class="sxs-lookup"><span data-stu-id="a091a-156">Global administrator name:</span></span> ![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="a091a-158">.onmicrosoft.com (с шага 6 этапа 1)</span><span class="sxs-lookup"><span data-stu-id="a091a-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="a091a-159">Кроме того, запишите пароль этой учетной записи в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="a091a-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="a091a-160">Название вашей организации:</span><span class="sxs-lookup"><span data-stu-id="a091a-160">Your trial subscription organization name:</span></span> ![Линия](../media/Common-Images/TableLine.png) <span data-ttu-id="a091a-162">(с шага 4 этапа 1)</span><span class="sxs-lookup"><span data-stu-id="a091a-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="a091a-163">Чтобы увидеть список учетных записей пользователей User 2, User 3, User 4 и User 5, выполните следующую команду в командной строке модуля Windows Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a091a-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="a091a-164">Запишите здесь имена учетных записей:</span><span class="sxs-lookup"><span data-stu-id="a091a-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="a091a-165">Имя учетной записи пользователя User 2: user2@</span><span class="sxs-lookup"><span data-stu-id="a091a-165">User 2 account name: user2@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="a091a-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a091a-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="a091a-168">Имя учетной записи пользователя User 3: user3@</span><span class="sxs-lookup"><span data-stu-id="a091a-168">User 3 account name: user3@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="a091a-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a091a-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="a091a-171">Имя учетной записи пользователя User 4: user4@</span><span class="sxs-lookup"><span data-stu-id="a091a-171">User 4 account name: user4@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="a091a-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a091a-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="a091a-174">Имя учетной записи пользователя User 5: user5@</span><span class="sxs-lookup"><span data-stu-id="a091a-174">User 5 account name: user5@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="a091a-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a091a-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="a091a-177">Кроме того, запишите в надежном месте общий пароль.</span><span class="sxs-lookup"><span data-stu-id="a091a-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="a091a-178">Использование среды тестирования Office 365</span><span class="sxs-lookup"><span data-stu-id="a091a-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="a091a-179">Если вам нужна только тестовая среда Office 365, прочитать оставшуюся часть этой статьи не нужно.</span><span class="sxs-lookup"><span data-stu-id="a091a-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="a091a-180">Дополнительные руководства по лаборатории тестирования, применимые к Office 365 и Microsoft 365, см. в руководстве по лаборатории тестирования [Microsoft 365 для предприятий.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="a091a-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="a091a-181">Этап 3. Добавление пробной подписки Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a091a-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="a091a-182">На этом этапе можно оформить пробную подписку Microsoft 365 E5 и добавить ее к той же организации, для которой создана пробная подписка на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="a091a-183">Сначала добавьте пробную подписку Microsoft 365 E5 и назначьте новую лицензию Microsoft 365 для учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a091a-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="a091a-184">В частном окне браузера используйте учетные данные глобального администратора, чтобы войти в Центр администрирования Microsoft 365 по вашему [https://admin.microsoft.com](https://admin.microsoft.com) сайту.</span><span class="sxs-lookup"><span data-stu-id="a091a-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="a091a-185">На странице **Центра администрирования Microsoft 365** в области навигации слева выберите "Выставление **> Приобретение служб".**</span><span class="sxs-lookup"><span data-stu-id="a091a-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="a091a-186">На странице **"Приобретение служб"** выберите **Microsoft 365 E5** и выберите **"Получить бесплатную пробную версия".**</span><span class="sxs-lookup"><span data-stu-id="a091a-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="a091a-187">На странице "Пробная версия **Microsoft 365 E5"** решите получить текстовое сообщение или телефонный звонок, введите номер телефона, а затем выберите "Sms **me"** или **"Позвонить мне".**</span><span class="sxs-lookup"><span data-stu-id="a091a-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="a091a-188">Выполните проверку.</span><span class="sxs-lookup"><span data-stu-id="a091a-188">Perform the verification.</span></span>

5. <span data-ttu-id="a091a-189">На странице **"Подтверждение заказа"** выберите **"Попробовать сейчас".**</span><span class="sxs-lookup"><span data-stu-id="a091a-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="a091a-190">На странице **квитанции** "Заказ" выберите **"Продолжить".**</span><span class="sxs-lookup"><span data-stu-id="a091a-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="a091a-191">В Центре администрирования Microsoft 365 выберите пользователей > **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="a091a-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="a091a-192">В **активных пользователях** выберите учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="a091a-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="a091a-193">Выберите **лицензии и приложения.**</span><span class="sxs-lookup"><span data-stu-id="a091a-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="a091a-194">Отключите лицензию для Office 365 корпоративный E5 и включите лицензию для Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="a091a-195">Выберите **"Сохранить изменения",** а затем закроем области сведений об учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="a091a-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="a091a-196">Затем повторите действия с 8 по 11 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).</span><span class="sxs-lookup"><span data-stu-id="a091a-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a091a-197">Срок действия пробной подписки microsoft 365 E5 составляет 30 дней.</span><span class="sxs-lookup"><span data-stu-id="a091a-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="a091a-198">Чтобы создать постоянную среду тестирования, переведите пробную подписку в платную подписку с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="a091a-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="a091a-199">Теперь ваша тестовая среда содержит:</span><span class="sxs-lookup"><span data-stu-id="a091a-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="a091a-200">Пробную подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="a091a-201">Все подходящие учетные записи пользователей (либо только глобального администратора или всех пяти пользователей), поддерживающие Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="a091a-202">Итоговая конфигурация, которая добавляет Microsoft 365 E5, выглядит так:</span><span class="sxs-lookup"><span data-stu-id="a091a-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Этап 3 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="a091a-204">Этап 4. Создание компьютера с ОС Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="a091a-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="a091a-205">На этом этапе мы создадим изолированный компьютер с Windows 10 Корпоративная в виде физического компьютера либо виртуальной машины (обычной или в Azure).</span><span class="sxs-lookup"><span data-stu-id="a091a-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="a091a-206">Физический компьютер</span><span class="sxs-lookup"><span data-stu-id="a091a-206">Physical computer</span></span>

<span data-ttu-id="a091a-207">На персональном компьютере установите Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="a091a-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="a091a-208">Пробную версия Windows 10 Корпоративная можно скачать [здесь.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)</span><span class="sxs-lookup"><span data-stu-id="a091a-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="a091a-209">Виртуальная машина</span><span class="sxs-lookup"><span data-stu-id="a091a-209">Virtual machine</span></span>

<span data-ttu-id="a091a-210">Создайте виртуальную машину с помощью гипервизора, а затем установите на нее Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="a091a-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="a091a-211">Пробную версия Windows 10 Корпоративная можно скачать [здесь.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)</span><span class="sxs-lookup"><span data-stu-id="a091a-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="a091a-212">Виртуальная машина в Azure</span><span class="sxs-lookup"><span data-stu-id="a091a-212">Virtual machine in Azure</span></span>

<span data-ttu-id="a091a-p111">Для создания виртуальной машины с Windows 10 в Microsoft Azure ***необходима подписка на основе Visual Studio*** с доступом к образу Windows 10 Корпоративная. В других типах подписок Azure, например пробной или платной, подобный доступ отсутствует. Последние сведения по этой теме см. в статье [Использование клиента Windows в Azure для сценариев разработки и тестирования](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="a091a-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a091a-216">Для указанных ниже последовательностей команд используется последняя версия Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a091a-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="a091a-217">См. ["Начало работы с помощью cmdlets Azure PowerShell".](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)</span><span class="sxs-lookup"><span data-stu-id="a091a-217">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="a091a-218">Эти наборы команд создают виртуальную машину под управлением Windows 10 Корпоративная с именем WIN10, а также всю необходимую инфраструктуру, включая группу ресурсов, учетную запись хранения и виртуальную сеть.</span><span class="sxs-lookup"><span data-stu-id="a091a-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="a091a-219">Если вы уже знакомы со службами инфраструктуры Azure, адаптируем эти инструкции в соответствии со своей развернутой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="a091a-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="a091a-220">Для начала запустите командную строку Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a091a-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="a091a-221">Войдите в свою учетную запись Azure с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="a091a-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="a091a-222">Получите имя подписки с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="a091a-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="a091a-223">Укажите свою подписку Azure.</span><span class="sxs-lookup"><span data-stu-id="a091a-223">Set your Azure subscription.</span></span> <span data-ttu-id="a091a-224">Замените все символы в кавычках правильным \< and > именем.</span><span class="sxs-lookup"><span data-stu-id="a091a-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="a091a-225">Затем создайте группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a091a-225">Next, create a new resource group.</span></span> <span data-ttu-id="a091a-226">Чтобы выбрать уникальное имя для группы ресурсов, с помощью этой команды отобразите имеющиеся группы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a091a-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="a091a-227">Создайте группу ресурсов с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="a091a-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="a091a-228">Замените все символы в кавычках \< and > правильными именами.</span><span class="sxs-lookup"><span data-stu-id="a091a-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="a091a-229">Затем создайте новую виртуальную сеть и виртуальную машину WIN10 с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="a091a-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="a091a-230">При появлении запроса укажите имя и пароль учетной записи локального администратора WIN10 и сохраните их в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="a091a-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="a091a-231">Этап 5. Присоединение компьютера с Windows 10 к Azure AD</span><span class="sxs-lookup"><span data-stu-id="a091a-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="a091a-232">После создания физической или виртуальной машины с Windows 10 Корпоративная войдите в систему, используя учетную запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="a091a-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a091a-233">Для виртуальной машины в Azure воспользуйтесь этими  [инструкциями,](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) чтобы подключиться к ней.</span><span class="sxs-lookup"><span data-stu-id="a091a-233">For a virtual machine in Azure, use  [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="a091a-234">Затем присоедините компьютер WIN10 к клиенту Azure AD, отвечающему за вашу подписку на Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a091a-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="a091a-235">На рабочем столе компьютера WIN10 выберите параметры start **> > Accounts > Access work or school > Connect.**</span><span class="sxs-lookup"><span data-stu-id="a091a-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="a091a-236">В **диалоговом окне "Настройка** учетной записи для работы или учебного заведения" выберите **"Присоединить это устройство к Azure Active Directory".**</span><span class="sxs-lookup"><span data-stu-id="a091a-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="a091a-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="a091a-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="a091a-238">Введите **пароль для** учетной записи глобального администратора и выберите **"Войти".**</span><span class="sxs-lookup"><span data-stu-id="a091a-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="a091a-239">Когда вам будет предложено убедиться, что это ваша организация, выберите **"Присоединиться"** и выберите **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="a091a-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="a091a-240">Закройте окно параметров.</span><span class="sxs-lookup"><span data-stu-id="a091a-240">Close the settings window.</span></span>
    
<span data-ttu-id="a091a-241">Затем установите приложения Microsoft 365 для предприятий на компьютере WIN10:</span><span class="sxs-lookup"><span data-stu-id="a091a-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="a091a-242">Откройте браузер Microsoft Edge и войте в Центр администрирования [Microsoft 365](https://admin.microsoft.com) учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a091a-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="a091a-243">На **вкладке Microsoft Office "Главная"** выберите **"Установить Office".**</span><span class="sxs-lookup"><span data-stu-id="a091a-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="a091a-244">Когда вам будет предложено что-то сделать, выберите "Выполнить", а затем выберите **"Да"** для контроля **учетных записей пользователей.**</span><span class="sxs-lookup"><span data-stu-id="a091a-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="a091a-245">Подождите, пока Office завершит установку.</span><span class="sxs-lookup"><span data-stu-id="a091a-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="a091a-246">When you see **You're all set!**, select **Close** twice.</span><span class="sxs-lookup"><span data-stu-id="a091a-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="a091a-247">Итоговая среда выглядит так:</span><span class="sxs-lookup"><span data-stu-id="a091a-247">Your resulting environment looks like this:</span></span>

![Этап 5 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="a091a-249">Эта среда включает компьютер с Windows 10, который:</span><span class="sxs-lookup"><span data-stu-id="a091a-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="a091a-250">присоединен к клиенту Azure AD, отвечающему за подписку Microsoft 365 E5;</span><span class="sxs-lookup"><span data-stu-id="a091a-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="a091a-251">зарегистрирован в Microsoft Intune (EMS) в качестве устройства Azure AD;</span><span class="sxs-lookup"><span data-stu-id="a091a-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="a091a-252">Установленные приложения Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="a091a-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="a091a-253">Теперь вы готовы поэкспериментировать с дополнительными функциями [Microsoft 365 для предприятий.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="a091a-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a091a-254">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a091a-254">Next steps</span></span>

<span data-ttu-id="a091a-255">Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:</span><span class="sxs-lookup"><span data-stu-id="a091a-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="a091a-256">Идентификация</span><span class="sxs-lookup"><span data-stu-id="a091a-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="a091a-257">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="a091a-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="a091a-258">Защита информации</span><span class="sxs-lookup"><span data-stu-id="a091a-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="a091a-259">См. также</span><span class="sxs-lookup"><span data-stu-id="a091a-259">See also</span></span>

[<span data-ttu-id="a091a-260">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="a091a-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a091a-261">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="a091a-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a091a-262">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="a091a-262">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
