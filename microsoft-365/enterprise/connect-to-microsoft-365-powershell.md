---
title: Подключение к Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Подключитесь к своему клиенту Microsoft 365, используя PowerShell для Microsoft 365, чтобы выполнять задачи администрирования из командной строки.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693310"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="330dc-103">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="330dc-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="330dc-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="330dc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="330dc-105">PowerShell для Microsoft 365 дает возможность настраивать параметры Microsoft 365 из командной строки.</span><span class="sxs-lookup"><span data-stu-id="330dc-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="330dc-106">Подключение к PowerShell — это простой процесс установки необходимого программного обеспечения и последующего подключения к организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="330dc-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="330dc-107">Существует две версии модуля PowerShell, которые используются для подключения к Microsoft 365 и управления учетными записями пользователей, группами и лицензиями:</span><span class="sxs-lookup"><span data-stu-id="330dc-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="330dc-108">Azure Active Directory PowerShell для Graph (командлеты содержат **AzureAD** в своем имени)</span><span class="sxs-lookup"><span data-stu-id="330dc-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="330dc-109">Модуль Microsoft Azure Active Directory для Windows PowerShell (командлеты содержат **MSol** в своем имени)</span><span class="sxs-lookup"><span data-stu-id="330dc-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="330dc-110">На момент выхода этой статьи модуль Azure Active Directory PowerShell для Graph не полностью заменяет функции командлетов модуля Microsoft Azure Active Directory для Windows PowerShell при администрировании пользователей, групп и лицензий.</span><span class="sxs-lookup"><span data-stu-id="330dc-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="330dc-111">В некоторых случаях необходимо использовать обе версии.</span><span class="sxs-lookup"><span data-stu-id="330dc-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="330dc-112">Вы можете безопасно установить обе версии на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="330dc-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="330dc-113">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="330dc-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="330dc-114">Ниже приведены версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="330dc-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="330dc-115">Windows 10, Windows 8.1, Windows 8 или Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="330dc-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="330dc-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="330dc-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="330dc-117">Для модуля Azure Active Directory PowerShell для Graph требуется использовать PowerShell версии 5.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="330dc-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="330dc-118">Для модуля Microsoft Azure Active Directory для Windows PowerShell требуется использовать PowerShell версии 5.1 или более поздней до PowerShell версии 6.</span><span class="sxs-lookup"><span data-stu-id="330dc-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="330dc-119">Вы не можете использовать PowerShell версии 7.</span><span class="sxs-lookup"><span data-stu-id="330dc-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="330dc-120">Для Windows 8.1, Windows 8, Windows 7 с пакетом обновления 1 (SP1), Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2 SP1 скачайте и установите [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="330dc-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="330dc-p104">Используйте 64-разрядную версию Windows. Поддержка 32-разрядной версии модуля Microsoft Azure Active Directory для Windows PowerShell прекращена в октябре 2014 г.</span><span class="sxs-lookup"><span data-stu-id="330dc-p104">Use a 64-bit version of Windows. Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="330dc-123">Эти процедуры предназначены для пользователей, которым назначена роль администраторов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="330dc-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="330dc-124">Дополнительные сведения см. в статье [О ролях администраторов](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="330dc-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="330dc-125">Подключение к модулю Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="330dc-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="330dc-126">Имена командлетов в модуле Azure Active Directory PowerShell для Graph включают компонент **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="330dc-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="330dc-127">Вы можете установить модуль [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) или [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span><span class="sxs-lookup"><span data-stu-id="330dc-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span></span>

<span data-ttu-id="330dc-128">Если процедурам требуются новые командлеты в модуле PowerShell Azure Active Directory для Graph, используйте эти действия, чтобы установить этот модуль и подключить его к вашей подписке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="330dc-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="330dc-129">Информацию о поддержке в различных версиях Microsoft Windows см. в [этой статье](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="330dc-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) for information about the support for different versions of Microsoft Windows.</span></span>
>

### <a name="step-1-install-required-software"></a><span data-ttu-id="330dc-130">Шаг 1. Установите необходимое программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="330dc-130">Step 1: Install required software</span></span>

<span data-ttu-id="330dc-p107">Указанные ниже действия необходимо выполнить на вашем компьютере только один раз (а не при каждом подключении). Тем не менее вам, скорее всего, придется периодически устанавливать более новые версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="330dc-p107">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="330dc-133">Откройте командную строку Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="330dc-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="330dc-134">В командном окне **Администратор: Windows PowerShell** выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="330dc-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="330dc-135">Если появится предупреждение об установке модуля из ненадежного репозитория, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="330dc-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="330dc-136">Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="330dc-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="330dc-137">Чтобы установить подключение к Azure AD для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell (не требуются расширенные права).</span><span class="sxs-lookup"><span data-stu-id="330dc-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="330dc-138">Облачная служба Office 365</span><span class="sxs-lookup"><span data-stu-id="330dc-138">Office 365 cloud</span></span> | <span data-ttu-id="330dc-139">Команда</span><span class="sxs-lookup"><span data-stu-id="330dc-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="330dc-140">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="330dc-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="330dc-141">Office 365, предоставляемый 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="330dc-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="330dc-142">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="330dc-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="330dc-143">Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="330dc-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="330dc-144">В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="330dc-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="330dc-145">Если вы используете многофакторную проверку подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.</span><span class="sxs-lookup"><span data-stu-id="330dc-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="330dc-146">После подключения можно использовать командлеты для [модуля Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="330dc-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="330dc-147">Подключение к модулю Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="330dc-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="330dc-148">Имена командлетов в модуле Microsoft Azure Active Directory для Windows PowerShell включают компонент **Msol**.</span><span class="sxs-lookup"><span data-stu-id="330dc-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="330dc-149">В PowerShell версии 7 и более поздних версиях не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="330dc-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="330dc-150">Для PowerShell версии 7 и более поздних версий требуется использовать модуль Azure Active Directory PowerShell для Graph или Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="330dc-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="330dc-151">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="330dc-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="330dc-152">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="330dc-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="330dc-153">Шаг 1. Установите необходимое программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="330dc-153">Step 1: Install required software</span></span>

<span data-ttu-id="330dc-p110">Указанные ниже действия необходимо выполнить на вашем компьютере только один раз (а не при каждом подключении). Тем не менее вам, скорее всего, придется периодически устанавливать более новые версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="330dc-p110">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="330dc-156">Если вы не используете операционную систему Windows 10, установите 64-разрядную версию помощника по входу в Microsoft Online Services. См. статью [Помощник по входу в Microsoft Online Services для ИТ-специалистов, RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="330dc-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="330dc-157">Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="330dc-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="330dc-158">Откройте командную строку Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="330dc-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="330dc-159">Выполните команду **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="330dc-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="330dc-160">Если отобразится запрос на установку поставщика NuGet, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="330dc-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="330dc-161">Если отобразится запрос на установку модуля из репозитория PSGallery, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="330dc-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="330dc-162">Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="330dc-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="330dc-163">Чтобы установить подключение к Azure AD для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell (не требуются расширенные права).</span><span class="sxs-lookup"><span data-stu-id="330dc-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="330dc-164">Облачная служба Office 365</span><span class="sxs-lookup"><span data-stu-id="330dc-164">Office 365 cloud</span></span> | <span data-ttu-id="330dc-165">Команда</span><span class="sxs-lookup"><span data-stu-id="330dc-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="330dc-166">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="330dc-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="330dc-167">Office 365, предоставляемый 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="330dc-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="330dc-168">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="330dc-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="330dc-169">Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="330dc-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="330dc-170">В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="330dc-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="330dc-171">Если вы используете многофакторную проверку подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.</span><span class="sxs-lookup"><span data-stu-id="330dc-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="330dc-172">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="330dc-172">How do you know this worked?</span></span>

<span data-ttu-id="330dc-173">Если при этом не возникают ошибки, подключение успешно установлено.</span><span class="sxs-lookup"><span data-stu-id="330dc-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="330dc-174">Для быстрой проверки можно запустить любой командлет Microsoft 365, например **Get-MsolUser**, и проверить результаты.</span><span class="sxs-lookup"><span data-stu-id="330dc-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="330dc-175">Если возникают ошибки, просмотрите список возможных причин ниже.</span><span class="sxs-lookup"><span data-stu-id="330dc-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="330dc-176">**Распространенная проблема  неправильный пароль.**.</span><span class="sxs-lookup"><span data-stu-id="330dc-176">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="330dc-177">Еще раз выполните шаг 2,</span><span class="sxs-lookup"><span data-stu-id="330dc-177">Run Step 2 again.</span></span> <span data-ttu-id="330dc-178">внимательно проверив вводимое имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="330dc-178">and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="330dc-179">**Для работы модуля Microsoft Azure Active Directory для Windows PowerShell необходимо, чтобы на вашем компьютере был включен компонент Microsoft .NET Framework 3.5.* x*. Скорее всего, на вашем компьютере установлена более новая версия этого компонента (например, 4 или 4.5.\* x\*), но вы можете включить или отключить режим обратной совместимости с более ранними версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="330dc-179">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="330dc-180">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="330dc-180">For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="330dc-181">[Включение .NET Framework 3.5 с помощью мастера добавления ролей и функций](https://go.microsoft.com/fwlink/p/?LinkId=532368) (Windows Server 2012 или Windows Server 2012 R2)</span><span class="sxs-lookup"><span data-stu-id="330dc-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="330dc-182">[Не удается открыть модуль Azure Active Directory для Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370) (Windows 7 или Windows Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="330dc-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="330dc-183">[Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10) (Windows 10, Windows 8.1 и Windows 8)</span><span class="sxs-lookup"><span data-stu-id="330dc-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="330dc-184">**Возможно, ваша версия модуля Microsoft Azure Active Directory для Windows PowerShell устарела.**</span><span class="sxs-lookup"><span data-stu-id="330dc-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="330dc-185">Чтобы проверить, выполните следующую команду в PowerShell для Microsoft 365 или в модуле Microsoft Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="330dc-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="330dc-186">Если возвращенный номер версии меньше 1.0.8070.2, удалите модуль Microsoft Azure Active Directory для Windows PowerShell и выполните установку с шага 1, описанного выше.</span><span class="sxs-lookup"><span data-stu-id="330dc-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="330dc-187">\*\*Если при подключении возникнет ошибка, ознакомьтесь с \*\*[этой статьей](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="330dc-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="330dc-188">**Если возникнет ошибка "Get-Item: не удается найти путь", используйте следующую команду:**</span><span class="sxs-lookup"><span data-stu-id="330dc-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="330dc-189">См. также</span><span class="sxs-lookup"><span data-stu-id="330dc-189">See also</span></span>

- [<span data-ttu-id="330dc-190">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="330dc-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="330dc-191">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="330dc-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="330dc-192">Подключение ко всем службам Microsoft 365 в одном окне Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="330dc-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
