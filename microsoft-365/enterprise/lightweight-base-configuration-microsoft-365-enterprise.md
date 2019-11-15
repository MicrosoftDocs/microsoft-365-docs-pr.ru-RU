---
title: Простая базовая конфигурация
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
ms.openlocfilehash: c654dc80620b98d09cf508e309d4410d9cf4a4dc
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639919"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="6a9fc-103">Простая базовая конфигурация</span><span class="sxs-lookup"><span data-stu-id="6a9fc-103">The lightweight base configuration</span></span>

<span data-ttu-id="6a9fc-104">В этой статье представлены пошаговые инструкции по созданию упрощенной среды с подпиской на Microsoft 365 E5 и компьютером с ОС Windows 10 Корпоративная.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-104">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![Простая среда тестирования Microsoft 365 корпоративный](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="6a9fc-106">В получившейся среде можно будет тестировать функции [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-106">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="6a9fc-108">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-108">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="6a9fc-109">Этап 1. Создание подписки на Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="6a9fc-109">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="6a9fc-110">Мы начнем с пробной подписки на Office 365 E5, а затем добавим к ней подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-110">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="6a9fc-111">Чтобы оформить пробную подписку на Office 365 E5, потребуются вымышленное название компании и новая учетная запись Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-111">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="6a9fc-p101">Рекомендуем использовать в качестве названия компании какую-нибудь вариацию имени Contoso (вымышленной компании, используемой в примерах от Майкрософт), но это необязательно. Запишите здесь название своей вымышленной компании: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="6a9fc-p102">Чтобы зарегистрировать новую учетную запись Майкрософт, перейдите на сайт [https://outlook.com](https://outlook.com) и создайте учетную запись, используя новый адрес электронной почты. Эта учетная запись будет использоваться для регистрации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="6a9fc-116">Запишите имя и фамилию новой учетной записи здесь: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="6a9fc-116">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="6a9fc-117">Запишите здесь адрес электронной почты новой учетной записи: ![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="6a9fc-117">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="6a9fc-118">Оформление пробной подписки на Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="6a9fc-118">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="6a9fc-119">Откройте на компьютере веб-браузер и перейдите на сайт [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-119">For the lightweight Office 365 dev/test environment, open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="6a9fc-120">На странице **приветствия** укажите:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-120">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="6a9fc-121">ваше физическое местонахождение;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-121">Your physical location</span></span>
    
  - <span data-ttu-id="6a9fc-122">имя и фамилию новой учетной записи Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-122">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="6a9fc-123">новый адрес электронной почты;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-123">Your new email account address</span></span>
    
  - <span data-ttu-id="6a9fc-124">рабочий телефон;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-124">A business phone number</span></span>
    
  - <span data-ttu-id="6a9fc-125">вымышленное название компании;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-125">Your fictional company name</span></span>
    
  - <span data-ttu-id="6a9fc-126">размер организации (250–999 человек).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-126">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="6a9fc-127">Нажмите **Еще одно действие**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-127">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="6a9fc-128">На странице **создание идентификатора пользователя** введите имя пользователя на основе нового адреса электронной почты, название вымышленной компании после знака @ (удалите все пробелы в названии) и пароль (дважды) для новой учетной записи Office 365. </span><span class="sxs-lookup"><span data-stu-id="6a9fc-128">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="6a9fc-129">Запишите пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-129">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="6a9fc-130">Запишите вымышленное название компании (**название организации**) здесь: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="6a9fc-130">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="6a9fc-131">Нажмите **Создать мою учетную запись**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-131">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="6a9fc-p103">На странице **Докажите. Что. Вы. Не. Робот.** введите номер телефона, поддерживающего текстовые сообщения, а затем нажмите **Отправить мне SMS**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p103">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="6a9fc-134">Введите код подтверждения из полученного SMS и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-134">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="6a9fc-135">Запишите здесь URL-адрес страницы входа (выделите и скопируйте): ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="6a9fc-135">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="6a9fc-136">Запишите здесь идентификатор пользователя (выделите и скопируйте): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6a9fc-136">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="6a9fc-137">Это значение будет называться **именем глобального администратора Office 365**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-137">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="6a9fc-138">Когда появится надпись **Все готово к работе**, нажмите ее.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-138">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="6a9fc-139">На следующей странице дождитесь завершения настройки Office 365 и появления всех плиток.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-139">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="6a9fc-140">Появится главная страница портала Office 365, с которой можно получить доступ к службам Office и Центру администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-140">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="6a9fc-141">Вы создали пробную подписку на Office 365, поэтому среда разработки и тестирования имеет собственный клиент Azure AD, отличный от использующихся для любых доступных платных подписок.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-141">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="6a9fc-142">Это разделение означает, что вы можете добавлять и удалять пользователей и группы в тестовом клиенте, никак не влияя на рабочие подписки.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-142">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="6a9fc-143">Этап 2. Настройка пробной подписки на Office 365</span><span class="sxs-lookup"><span data-stu-id="6a9fc-143">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="6a9fc-144">На этом этапе настраивается подписка на Office 365 с дополнительными пользователями, этим пользователям назначаются лицензии Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-144">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="6a9fc-145">Следуйте указаниям в статье [Подключение к Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module), чтобы подключиться к подписке на Office 365 с модулем PowerShell Azure Active Directory для Graph с вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-145">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="6a9fc-146">В диалоговом окне "Запрос учетных данных Windows PowerShell" введите имя глобального администратора Office 365 (например, jdoe@contosotoycompany.onmicrosoft.com) и пароль.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-146">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="6a9fc-147">Введите название организации (например, contosotoycompany), двузначный код страны и пароль обычной учетной записи, а затем выполните следующие команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-147">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="6a9fc-148">Общий пароль используется для автоматизации и упрощения конфигурации среды разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-148">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="6a9fc-149">Очевидно, что это не рекомендуется в производственных подписках.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-149">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="6a9fc-150">Запишите важнейшую информацию для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-150">Record key information for future reference</span></span>

<span data-ttu-id="6a9fc-151">Вы можете напечатать эту статью, чтобы записать информацию, которая понадобится вам этой среды в течение 30 дней пробной подписки на Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-151">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="6a9fc-152">Пробную подписку можно легко продлить еще на 30 дней.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-152">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="6a9fc-153">Чтобы создать постоянную среду тестирования и разработки, создайте новую платную подписку с отдельным клиентом Azure AD и с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-153">For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span>

<span data-ttu-id="6a9fc-154">Запишите найти эти значения:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-154">Record these values:</span></span>
  
- <span data-ttu-id="6a9fc-155">Имя глобального администратора Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (с шага 9 этапа 2)</span><span class="sxs-lookup"><span data-stu-id="6a9fc-155">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="6a9fc-156">Кроме того, запишите пароль этой учетной записи в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-156">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="6a9fc-157">Название организации с пробной подпиской: ![](./media/Common-Images/TableLine.png) (с шага 4 этапа 2)</span><span class="sxs-lookup"><span data-stu-id="6a9fc-157">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="6a9fc-158">Чтобы увидеть список учетных записей пользователей User 2, User 3, User 4 и User 5, выполните следующую команду в командной строке модуля Windows Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-158">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="6a9fc-159">Запишите здесь имена учетных записей:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-159">Record the account names here:</span></span>
    
  - <span data-ttu-id="6a9fc-160">Имя учетной записи пользователя User 2: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6a9fc-160">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="6a9fc-161">Имя учетной записи пользователя User 3: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6a9fc-161">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="6a9fc-162">Имя учетной записи пользователя User 4: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6a9fc-162">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="6a9fc-163">Имя учетной записи пользователя User 5: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6a9fc-163">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="6a9fc-164">Кроме того, запишите в надежном месте общий пароль.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-164">Also record the passwords for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-devtest-environment"></a><span data-ttu-id="6a9fc-165">Использование среды разработки и тестирования Office 365</span><span class="sxs-lookup"><span data-stu-id="6a9fc-165">Phase 1: Create an Office 365 dev/test environment</span></span>

<span data-ttu-id="6a9fc-166">Если вам требуется только среда разработки и тестирования Office 365, то на этом можно остановиться.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-166">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="6a9fc-167">См. [Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md) для получения дополнительных руководств по лаборатории тестирования, применимых одновременно к Office 365 и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-167">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="6a9fc-168">Этап 3. Добавление пробной подписки Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6a9fc-168">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="6a9fc-169">На этом этапе можно оформить пробную подписку Microsoft 365 E5 и добавить ее к той же организации, для которой создана пробная подписка на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-169">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="6a9fc-170">Сначала добавьте пробную подписку Microsoft 365 E5 и назначьте лицензию Microsoft 365 для учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-170">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="6a9fc-171">С помощью закрытого экземпляра интернет-браузера войдите в Центр администрирования Microsoft 365 [https://admin.microsoft.com](https://admin.microsoft.com), используя данные учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-171">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="6a9fc-172">На странице **Центра администрирования Microsoft 365**, в области навигации слева, нажмите **Выставление счетов > Приобретение служб**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-172">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="6a9fc-173">На странице **Приобретение служб** найдите пункт **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-173">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="6a9fc-174">Наведите на него указатель мыши и выберите **Начать бесплатный пробный период**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-174">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="6a9fc-175">На странице **Пробная версия Microsoft 365 E5** выберите текстовое сообщение или звонок, введите свой номер телефона, затем нажмите кнопку **Отправить сообщение** или **Позвонить мне**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-175">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="6a9fc-176">На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-176">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="6a9fc-177">На странице **Получение заказа** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-177">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="6a9fc-178">В центре администрирования Microsoft 365 щелкните **Активные пользователи**, а учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-178">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="6a9fc-179">Нажмите **Изменить\*\*\*\*лицензии продукта**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-179">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="6a9fc-180">Отключите лицензию для Office 365 корпоративный E5 и включите лицензию для Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-180">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="6a9fc-181">Нажмите **Сохранить и закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-181">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="6a9fc-182">Затем повторите действия с 8 по 11 из предыдущей процедуры для всех остальных учетных записей (User 2, User 3, User 4 и User 5).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-182">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a9fc-183">Период действия пробной подписки Microsoft 365 E5 равен 30 дням.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-183">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="6a9fc-184">Для среды постоянного тестирования переведите пробную подписку в платную подписку с небольшим количеством лицензий.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-184">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="6a9fc-185">Теперь ваша тестовая среда содержит:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-185">Your test environment now has:</span></span>
  
- <span data-ttu-id="6a9fc-186">Пробную подписку Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-186">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="6a9fc-187">Все подходящие учетные записи пользователей (либо только глобального администратора или всех пяти пользователей), поддерживающие Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-187">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="6a9fc-188">Здесь показана итоговая конфигурация с добавлением Microsoft 365 E5, включающая Office 365 и Enterprise Security + Management (EMS).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-188">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Этап 2 разработки тестовой среды, включающей Microsoft 365 корпоративный](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="6a9fc-190">Этап 4. Создание компьютера с ОС Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="6a9fc-190">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="6a9fc-191">На этом этапе мы создадим изолированный компьютер с Windows 10 Корпоративная в виде физического компьютера либо виртуальной машины (обычной или в Azure).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-191">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="6a9fc-192">Физический компьютер</span><span class="sxs-lookup"><span data-stu-id="6a9fc-192">Physical computer</span></span>

<span data-ttu-id="6a9fc-p109">Установите Windows 10 Корпоративная на персональном компьютере. Пробную версию Windows 10 Корпоративная можно скачать [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="6a9fc-195">Виртуальная машина</span><span class="sxs-lookup"><span data-stu-id="6a9fc-195">Virtual machine</span></span>

<span data-ttu-id="6a9fc-p110">Создайте виртуальную машину с помощью выбранного гипервизора и установите на него Windows 10 Корпоративная. Пробную версию Windows 10 Корпоративная можно скачать [здесь](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="6a9fc-198">Виртуальная машина в Azure</span><span class="sxs-lookup"><span data-stu-id="6a9fc-198">Virtual machine in Azure</span></span>

<span data-ttu-id="6a9fc-p111">Для создания виртуальной машины с Windows 10 в Microsoft Azure ***необходима подписка на основе Visual Studio*** с доступом к образу Windows 10 Корпоративная. В других типах подписок Azure, например пробной или платной, подобный доступ отсутствует. Последние сведения по этой теме см. в статье [Использование клиента Windows в Azure для сценариев разработки и тестирования](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a9fc-p112">Для приведенных ниже последовательностей команд используется последняя версия Azure PowerShell. См. статью [Начало работы с командлетами Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Эти наборы команд создают виртуальную машину под управлением Windows 10 Корпоративная с именем WIN10, а также всю необходимую инфраструктуру, включая группу ресурсов, учетную запись хранения и виртуальную сеть. Если вы уже знакомы со службами инфраструктуры Azure, адаптируйте эти инструкции в соответствии с вашей развернутой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="6a9fc-206">Для начала запустите командную строку Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-206">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="6a9fc-207">Войдите в свою учетную запись Azure с помощью указанной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-207">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="6a9fc-208">Получите имя подписки с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-208">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="6a9fc-p113">Укажите свою подписку Azure. Замените текст в кавычках, в том числе символы "\<" и ">", на правильное имя.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="6a9fc-p114">Затем создайте группу ресурсов. Чтобы выбрать уникальное имя для группы ресурсов, с помощью этой команды выведите имеющиеся группы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="6a9fc-p115">Создайте группу ресурсов с помощью приведенных ниже команд. Замените все символы в кавычках (в том числе символы "\<" и ">") на правильные имена.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="6a9fc-p116">Далее используйте приведенные ниже команды для создания новой виртуальной сети и виртуальной машины WIN10. При появлении запроса укажите имя и пароль учетной записи локального администратора WIN10 и сохраните их в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="6a9fc-217">Этап 5. Присоединение компьютера с Windows 10 к Azure AD</span><span class="sxs-lookup"><span data-stu-id="6a9fc-217">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="6a9fc-218">После создания физической или виртуальной машины с Windows 10 Корпоративная войдите в систему, используя учетную запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-218">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a9fc-219">Чтобы подключиться к виртуальной машине в Azure, следуйте [этим инструкциям](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-219">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="6a9fc-220">Затем присоедините компьютер WIN10 к клиенту Azure AD, отвечающему за вашу подписку на Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-220">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="6a9fc-221">На рабочем столе компьютера WIN10 нажмите **Пуск > Параметры > Учетные записи > Доступ к учетной записи места работы или учебного заведения > Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-221">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="6a9fc-222">В диалоговом окне **Настройка рабочей или учебной учетной записи** нажмите **Присоединить это устройство к Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-222">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="6a9fc-223">В диалоговом окне **Рабочая или учебная учетная запись** введите имя учетной записи глобального администратора подписки на Microsoft 365 E5 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-223">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="6a9fc-224">В поле **Введите пароль** укажите пароль к учетной записи глобального администратора, а затем нажмите кнопку **Войти**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-224">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="6a9fc-225">Чтобы убедиться, что это ваша организация, нажмите кнопку **Присоединиться**, а затем нажмите**Готово**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-225">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="6a9fc-226">Закройте окно параметров.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-226">Close the settings window.</span></span>
    
<span data-ttu-id="6a9fc-227">Затем установите Office 365 профессиональный плюс на компьютер WIN10</span><span class="sxs-lookup"><span data-stu-id="6a9fc-227">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="6a9fc-228">Откройте браузер Microsoft Edge и войдите в портал Office 365 с данными учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-228">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="6a9fc-229">Дополнительные сведения см. в статье [Вход в Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-229">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="6a9fc-230">На главной вкладке **Microsoft Office** нажмите **Установить Office**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-230">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="6a9fc-231">Когда вам будет предложено выбрать действие, нажмите кнопку **Выполнить**, а затем выберите **Да** для пункта **Контроль учетных записей**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-231">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="6a9fc-p118">Подождите, пока Office завершит установку. Увидев оповещение **Настройка завершена**, дважды нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="6a9fc-234">Ниже показана итоговая среда.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-234">Here is your resulting configuration.</span></span>

![Этап 5 разработки тестовой среды, включающей Microsoft 365 корпоративный](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="6a9fc-236">Эта среда включает компьютер с Windows 10, который:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-236">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="6a9fc-237">присоединен к клиенту Azure AD, отвечающему за подписку Microsoft 365 E5;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-237">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="6a9fc-238">зарегистрирован в Microsoft Intune (EMS) в качестве устройства Azure AD;</span><span class="sxs-lookup"><span data-stu-id="6a9fc-238">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="6a9fc-239">содержит установленный набор Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="6a9fc-239">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="6a9fc-240">Теперь вы можете экспериментировать с дополнительными возможностями [Microsoft 365 корпоративный](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="6a9fc-240">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="6a9fc-241">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6a9fc-241">Next steps</span></span>

<span data-ttu-id="6a9fc-242">Ознакомьтесь с этими дополнительными комплектами руководств по лаборатории тестирования:</span><span class="sxs-lookup"><span data-stu-id="6a9fc-242">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="6a9fc-243">Идентификация</span><span class="sxs-lookup"><span data-stu-id="6a9fc-243">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="6a9fc-244">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="6a9fc-244">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="6a9fc-245">Защита информации</span><span class="sxs-lookup"><span data-stu-id="6a9fc-245">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="6a9fc-246">См. также</span><span class="sxs-lookup"><span data-stu-id="6a9fc-246">See also</span></span>

[<span data-ttu-id="6a9fc-247">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a9fc-247">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6a9fc-248">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a9fc-248">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6a9fc-249">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a9fc-249">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
