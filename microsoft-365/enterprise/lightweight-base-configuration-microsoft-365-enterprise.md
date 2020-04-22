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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Это руководство по лаборатории тестирования поможет вам создать простую тестовую среду для Microsoft 365 корпоративный.
ms.openlocfilehash: 04e63b1c3d9d35bd636041f8be7655ab17b1d165
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631613"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="160d0-103">Простая базовая конфигурация</span><span class="sxs-lookup"><span data-stu-id="160d0-103">The lightweight base configuration</span></span>

<span data-ttu-id="160d0-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="160d0-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="160d0-105">В этой статье представлены пошаговые инструкции по созданию упрощенной среды с подпиской на Microsoft 365 E5 и компьютером с ОС Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="160d0-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![Простая среда тестирования Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="160d0-107">В получившейся среде можно будет тестировать функции [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="160d0-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="160d0-109">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="160d0-109">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="160d0-110">Этап 1. Создание подписки на Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="160d0-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="160d0-111">Мы начнем с пробной подписки на Office 365 E5, а затем добавим к ней подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="160d0-112">Чтобы оформить пробную подписку на Office 365 E5, потребуются вымышленное название компании и новая учетная запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="160d0-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="160d0-p101">Рекомендуем использовать в качестве названия компании какую-нибудь вариацию имени Contoso (вымышленной компании, используемой в примерах от Майкрософт), но это необязательно. Запишите здесь название своей вымышленной компании:</span><span class="sxs-lookup"><span data-stu-id="160d0-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![Линия](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="160d0-p102">Чтобы зарегистрировать новую учетную запись Майкрософт, перейдите на сайт [https://outlook.com](https://outlook.com) и создайте учетную запись, используя новый адрес электронной почты. Эта учетная запись будет использоваться для регистрации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d0-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="160d0-118">Запишите здесь имя и фамилию для новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="160d0-118">Record the first and last name of your new account here:</span></span> ![Линия](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="160d0-120">Запишите здесь адрес электронной почты новой учетной записи:</span><span class="sxs-lookup"><span data-stu-id="160d0-120">Record the new email account address here:</span></span> ![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="160d0-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="160d0-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="160d0-123">Оформление пробной подписки на Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="160d0-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="160d0-124">Откройте на компьютере веб-браузер и перейдите на сайт [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="160d0-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="160d0-125">На странице **Благодарим за выбор Office 365 E5** укажите свой новый адрес учетной записи электронной почты на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="160d0-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="160d0-126">На шаге 2 процесса подписки введите требуемую информацию и выполните проверку.</span><span class="sxs-lookup"><span data-stu-id="160d0-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="160d0-127">На шаге 3 введите название организации и имя учетной записи для глобального администратора подписки.</span><span class="sxs-lookup"><span data-stu-id="160d0-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="160d0-128">Запишите сведения страницы входа (выделите и скопируйте) с шага 4 здесь:</span><span class="sxs-lookup"><span data-stu-id="160d0-128">For step 4, record the sign-in page here (select and copy):</span></span> ![Линия](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="160d0-130">Запишите здесь идентификатор пользователя: ![Линия](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="160d0-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="160d0-131">Запишите пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="160d0-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="160d0-132">Это значение будет называться **именем глобального администратора**.</span><span class="sxs-lookup"><span data-stu-id="160d0-132">This value will be referred to as the **global administrator name**.</span></span>
8. <span data-ttu-id="160d0-133">Нажмите кнопку **Перейти к программе установки**.</span><span class="sxs-lookup"><span data-stu-id="160d0-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="160d0-134">На странице установки Office 365 E5 установите флажок **Продолжить использование домена *ваша организация*.onmicrosoft.com для электронной почты и входа** и щелкните ссылку **Выйти и продолжить позже**.</span><span class="sxs-lookup"><span data-stu-id="160d0-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="160d0-135">Должен открыться Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="160d0-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="160d0-136">Вы создали пробную подписку на Office 365, поэтому среда тестирования имеет собственный клиент Azure AD, отличный от использующихся для любых доступных платных подписок.</span><span class="sxs-lookup"><span data-stu-id="160d0-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="160d0-137">Это разделение означает, что вы можете добавлять и удалять пользователей и группы в тестовом клиенте, никак не влияя на рабочие подписки.</span><span class="sxs-lookup"><span data-stu-id="160d0-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="160d0-138">Этап 2. Настройка пробной подписки на Office 365</span><span class="sxs-lookup"><span data-stu-id="160d0-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="160d0-139">На этом этапе настраивается подписка с дополнительными пользователями, этим пользователям назначаются лицензии Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-139">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="160d0-140">Следуйте указаниям в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module), чтобы подключиться к подписке с модулем PowerShell Azure Active Directory для Graph с вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="160d0-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="160d0-141">В диалоговом окне **Запрос учетных данных Windows PowerShell** введите имя глобального администратора (например, jdoe@contosotoycompany.onmicrosoft.com) и пароль.</span><span class="sxs-lookup"><span data-stu-id="160d0-141">In the **Windows PowerShell Credential Request** dialog box, type the global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="160d0-142">Введите название организации (например, contosotoycompany), двузначный код страны и пароль обычной учетной записи, а затем выполните следующие команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="160d0-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="160d0-143">Общий пароль используется для автоматизации и упрощения конфигурации среды тестирования.</span><span class="sxs-lookup"><span data-stu-id="160d0-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="160d0-144">Очевидно, что это не рекомендуется в производственных подписках.</span><span class="sxs-lookup"><span data-stu-id="160d0-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="160d0-145">Запишите важнейшую информацию для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="160d0-145">Record key information for future reference</span></span>

<span data-ttu-id="160d0-146">Можно напечатать эту статью, чтобы записать информацию, которая понадобится вам для этой среды в течение 30 дней пробной подписки на Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d0-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="160d0-147">Пробную подписку можно легко продлить еще на 30 дней.</span><span class="sxs-lookup"><span data-stu-id="160d0-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="160d0-148">Чтобы создать постоянную среду тестирования, создайте новую платную подписку с отдельным клиентом Azure AD и с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="160d0-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="160d0-149">Запишите эти значения:</span><span class="sxs-lookup"><span data-stu-id="160d0-149">Record these values:</span></span>
  
- <span data-ttu-id="160d0-150">Имя глобального администратора:</span><span class="sxs-lookup"><span data-stu-id="160d0-150">global administrator name:</span></span> ![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="160d0-152">.onmicrosoft.com (с шага 6 этапа 1)</span><span class="sxs-lookup"><span data-stu-id="160d0-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="160d0-153">Кроме того, запишите пароль этой учетной записи в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="160d0-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="160d0-154">Название вашей организации:</span><span class="sxs-lookup"><span data-stu-id="160d0-154">Your trial subscription organization name:</span></span> ![Линия](../media/Common-Images/TableLine.png) <span data-ttu-id="160d0-156">(с шага 4 этапа 1)</span><span class="sxs-lookup"><span data-stu-id="160d0-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="160d0-157">Чтобы увидеть список учетных записей пользователей User 2, User 3, User 4 и User 5, выполните следующую команду в командной строке модуля Windows Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="160d0-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="160d0-158">Запишите здесь имена учетных записей:</span><span class="sxs-lookup"><span data-stu-id="160d0-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="160d0-159">Имя учетной записи пользователя User 2: user2@</span><span class="sxs-lookup"><span data-stu-id="160d0-159">User 2 account name: user2@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="160d0-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="160d0-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="160d0-162">Имя учетной записи пользователя User 3: user3@</span><span class="sxs-lookup"><span data-stu-id="160d0-162">User 3 account name: user3@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="160d0-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="160d0-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="160d0-165">Имя учетной записи пользователя User 4: user4@</span><span class="sxs-lookup"><span data-stu-id="160d0-165">User 4 account name: user4@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="160d0-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="160d0-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="160d0-168">Имя учетной записи пользователя User 5: user5@</span><span class="sxs-lookup"><span data-stu-id="160d0-168">User 5 account name: user5@</span></span>![Линия](../media/Common-Images/TableLine.png)<span data-ttu-id="160d0-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="160d0-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="160d0-171">Кроме того, запишите в надежном месте общий пароль.</span><span class="sxs-lookup"><span data-stu-id="160d0-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="160d0-172">Использование среды тестирования Office 365</span><span class="sxs-lookup"><span data-stu-id="160d0-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="160d0-173">Если вам требуется только среда тестирования Office 365, на этом можно остановиться.</span><span class="sxs-lookup"><span data-stu-id="160d0-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="160d0-174">См. [Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для получения дополнительных руководств по лаборатории тестирования, применимых одновременно к Office 365 и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="160d0-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="160d0-175">Этап 3. Добавление пробной подписки Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="160d0-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="160d0-176">На этом этапе можно оформить пробную подписку Microsoft 365 E5 и добавить ее к той же организации, для которой создана пробная подписка на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="160d0-177">Сначала добавьте пробную подписку Microsoft 365 E5 и назначьте новую лицензию Microsoft 365 для учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="160d0-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="160d0-178">С помощью приватной сессии интернет-браузера войдите в Центр администрирования Microsoft 365 [https://admin.microsoft.com](https://admin.microsoft.com), используя данные учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="160d0-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="160d0-179">На странице **Центра администрирования Microsoft 365**, в области навигации слева, нажмите **Выставление счетов > Приобретение служб**.</span><span class="sxs-lookup"><span data-stu-id="160d0-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="160d0-180">На странице **Приобретение служб** выберите **Microsoft 365 E5** и щелкните **Бесплатная пробная версия**.</span><span class="sxs-lookup"><span data-stu-id="160d0-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="160d0-181">На странице **Пробная версия Microsoft 365 E5** выберите текстовое сообщение или звонок, введите свой номер телефона, затем нажмите кнопку **Отправить сообщение** или **Позвонить мне**.</span><span class="sxs-lookup"><span data-stu-id="160d0-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="160d0-182">Выполните проверку.</span><span class="sxs-lookup"><span data-stu-id="160d0-182">Perform the verification.</span></span>

5. <span data-ttu-id="160d0-183">На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.</span><span class="sxs-lookup"><span data-stu-id="160d0-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="160d0-184">На странице **Получение заказа** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="160d0-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="160d0-185">В Центре администрирования Microsoft 365 выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="160d0-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="160d0-186">На странице **Активные пользователи** выберите свою учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="160d0-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="160d0-187">Щелкните **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="160d0-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="160d0-188">Отключите лицензию для Office 365 корпоративный E5 и включите лицензию для Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="160d0-189">Нажмите кнопку **Сохранить изменения** и закройте область сведений об учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="160d0-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="160d0-190">Затем повторите действия с 8 по 11 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).</span><span class="sxs-lookup"><span data-stu-id="160d0-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="160d0-191">Период действия пробной подписки Microsoft 365 E5 равен 30 дням.</span><span class="sxs-lookup"><span data-stu-id="160d0-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="160d0-192">Чтобы создать постоянную среду тестирования, переведите пробную подписку в платную подписку с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="160d0-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="160d0-193">Теперь ваша тестовая среда содержит:</span><span class="sxs-lookup"><span data-stu-id="160d0-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="160d0-194">Пробную подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="160d0-195">Все подходящие учетные записи пользователей (либо только глобального администратора или всех пяти пользователей), поддерживающие Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="160d0-196">Здесь показана итоговая конфигурация с добавлением Microsoft 365 E5, включающая Office 365 и Enterprise Security + Management (EMS).</span><span class="sxs-lookup"><span data-stu-id="160d0-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Этап 3 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="160d0-198">Этап 4. Создание компьютера с ОС Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="160d0-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="160d0-199">На этом этапе мы создадим изолированный компьютер с Windows 10 Корпоративная в виде физического компьютера либо виртуальной машины (обычной или в Azure).</span><span class="sxs-lookup"><span data-stu-id="160d0-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="160d0-200">Физический компьютер</span><span class="sxs-lookup"><span data-stu-id="160d0-200">Physical computer</span></span>

<span data-ttu-id="160d0-p109">Установите Windows 10 Корпоративная на персональном компьютере. Пробную версию Windows 10 Корпоративная можно скачать [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="160d0-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="160d0-203">Виртуальная машина</span><span class="sxs-lookup"><span data-stu-id="160d0-203">Virtual machine</span></span>

<span data-ttu-id="160d0-p110">Создайте виртуальную машину с помощью выбранного гипервизора и установите на него Windows 10 Корпоративная. Пробную версию Windows 10 Корпоративная можно скачать [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="160d0-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="160d0-206">Виртуальная машина в Azure</span><span class="sxs-lookup"><span data-stu-id="160d0-206">Virtual machine in Azure</span></span>

<span data-ttu-id="160d0-p111">Для создания виртуальной машины с Windows 10 в Microsoft Azure ***необходима подписка на основе Visual Studio*** с доступом к образу Windows 10 Корпоративная. В других типах подписок Azure, например пробной или платной, подобный доступ отсутствует. Последние сведения по этой теме см. в статье [Использование клиента Windows в Azure для сценариев разработки и тестирования](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="160d0-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="160d0-p112">Для приведенных ниже последовательностей команд используется последняя версия Azure PowerShell. См. статью [Начало работы с командлетами Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Эти наборы команд создают виртуальную машину под управлением Windows 10 Корпоративная с именем WIN10, а также всю необходимую инфраструктуру, включая группу ресурсов, учетную запись хранения и виртуальную сеть. Если вы уже знакомы со службами инфраструктуры Azure, адаптируйте эти инструкции в соответствии с вашей развернутой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="160d0-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="160d0-214">Для начала запустите командную строку Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="160d0-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="160d0-215">Войдите в свою учетную запись Azure с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="160d0-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="160d0-216">Получите имя подписки с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="160d0-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="160d0-p113">Укажите свою подписку Azure. Замените текст в кавычках, в том числе символы "\<" и ">", на правильное имя.</span><span class="sxs-lookup"><span data-stu-id="160d0-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="160d0-p114">Затем создайте группу ресурсов. Чтобы выбрать уникальное имя для группы ресурсов, с помощью этой команды выведите имеющиеся группы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="160d0-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="160d0-p115">Создайте группу ресурсов с помощью приведенных ниже команд. Замените все символы в кавычках (в том числе символы "\<" и ">") на правильные имена.</span><span class="sxs-lookup"><span data-stu-id="160d0-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="160d0-p116">Далее используйте приведенные ниже команды для создания новой виртуальной сети и виртуальной машины WIN10. При появлении запроса укажите имя и пароль учетной записи локального администратора WIN10 и сохраните их в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="160d0-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="160d0-225">Этап 5. Присоединение компьютера с Windows 10 к Azure AD</span><span class="sxs-lookup"><span data-stu-id="160d0-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="160d0-226">После создания физической или виртуальной машины с Windows 10 Корпоративная войдите в систему, используя учетную запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="160d0-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="160d0-227">Чтобы подключиться к виртуальной машине в Azure, следуйте [этим инструкциям](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="160d0-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="160d0-228">Затем присоедините компьютер WIN10 к клиенту Azure AD, отвечающему за вашу подписку на Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="160d0-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="160d0-229">На рабочем столе компьютера WIN10 нажмите **Пуск > Параметры > Учетные записи > Доступ к учетной записи места работы или учебного заведения > Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="160d0-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="160d0-230">В диалоговом окне **Настройка рабочей или учебной учетной записи** нажмите **Присоединить это устройство к Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="160d0-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="160d0-231">В диалоговом окне **Рабочая или учебная учетная запись** введите имя учетной записи глобального администратора подписки на Microsoft 365 E5 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="160d0-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="160d0-232">В поле **Введите пароль** укажите пароль к учетной записи глобального администратора, а затем нажмите кнопку **Войти**.</span><span class="sxs-lookup"><span data-stu-id="160d0-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="160d0-233">Чтобы убедиться, что это ваша организация, нажмите кнопку **Присоединиться**, а затем нажмите**Готово**.</span><span class="sxs-lookup"><span data-stu-id="160d0-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="160d0-234">Закройте окно параметров.</span><span class="sxs-lookup"><span data-stu-id="160d0-234">Close the settings window.</span></span>
    
<span data-ttu-id="160d0-235">Затем установите приложения Microsoft 365 для предприятий на компьютер WIN10.</span><span class="sxs-lookup"><span data-stu-id="160d0-235">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="160d0-236">Откройте браузер Microsoft Edge и войдите в портал Office 365 с данными учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="160d0-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="160d0-237">Дополнительные сведения см. в статье [Вход в Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="160d0-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="160d0-238">На главной вкладке **Microsoft Office** нажмите **Установить Office**.</span><span class="sxs-lookup"><span data-stu-id="160d0-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="160d0-239">Когда вам будет предложено выбрать действие, нажмите кнопку **Выполнить**, а затем выберите **Да** для пункта **Контроль учетных записей**.</span><span class="sxs-lookup"><span data-stu-id="160d0-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="160d0-p118">Подождите, пока Office завершит установку. Увидев оповещение **Настройка завершена**, дважды нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="160d0-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="160d0-242">Ниже показана итоговая среда.</span><span class="sxs-lookup"><span data-stu-id="160d0-242">Here is your resulting environment.</span></span>

![Этап 5 разработки тестовой среды, включающей Microsoft 365 корпоративный](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="160d0-244">Эта среда включает компьютер с Windows 10, который:</span><span class="sxs-lookup"><span data-stu-id="160d0-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="160d0-245">присоединен к клиенту Azure AD, отвечающему за подписку Microsoft 365 E5;</span><span class="sxs-lookup"><span data-stu-id="160d0-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="160d0-246">зарегистрирован в Microsoft Intune (EMS) в качестве устройства Azure AD;</span><span class="sxs-lookup"><span data-stu-id="160d0-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="160d0-247">установлены приложения Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="160d0-247">Has Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="160d0-248">Теперь вы можете экспериментировать с дополнительными возможностями [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="160d0-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="160d0-249">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="160d0-249">Next steps</span></span>

<span data-ttu-id="160d0-250">Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:</span><span class="sxs-lookup"><span data-stu-id="160d0-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="160d0-251">Идентификация</span><span class="sxs-lookup"><span data-stu-id="160d0-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="160d0-252">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="160d0-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="160d0-253">Защита информации</span><span class="sxs-lookup"><span data-stu-id="160d0-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="160d0-254">См. также</span><span class="sxs-lookup"><span data-stu-id="160d0-254">See also</span></span>

[<span data-ttu-id="160d0-255">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="160d0-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="160d0-256">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="160d0-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="160d0-257">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="160d0-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
