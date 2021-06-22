---
title: Подключение к Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Подключитесь к клиенту Microsoft 365, используя PowerShell для Microsoft 365, чтобы выполнять задачи администрирования из командной строки.
ms.openlocfilehash: 6b8f98441c7d727984bde8775dea496a9324d50c
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053063"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="1e70c-103">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e70c-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="1e70c-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1e70c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1e70c-105">С помощью PowerShell для Microsoft 365 можно управлять параметрами Microsoft 365 из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1e70c-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="1e70c-106">Для подключения к PowerShell достаточно лишь установить необходимое программное обеспечения, а затем подключиться к организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="1e70c-107">Существует две версии модуля PowerShell, которые используются для подключения к Microsoft 365 и управления учетными записями пользователей, группами и лицензиями:</span><span class="sxs-lookup"><span data-stu-id="1e70c-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="1e70c-108">Azure Active Directory PowerShell для Graph (имена командлетов содержат *AzureAD*)</span><span class="sxs-lookup"><span data-stu-id="1e70c-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="1e70c-109">Модуль Microsoft Azure Active Directory для Windows PowerShell (имена командлетов содержат *Msol*)</span><span class="sxs-lookup"><span data-stu-id="1e70c-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="1e70c-110">В настоящее время модуль Azure Active Directory PowerShell для Graph не полностью заменяет функциональность модуля Microsoft Azure Active Directory для Windows PowerShell в отношении администрирования пользователей, групп и лицензий.</span><span class="sxs-lookup"><span data-stu-id="1e70c-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="1e70c-111">В некоторых случаях необходимо использовать обе версии.</span><span class="sxs-lookup"><span data-stu-id="1e70c-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="1e70c-112">Вы можете безопасно установить обе версии на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1e70c-112">You can safely install both versions on the same computer.</span></span>

>[!Note]
><span data-ttu-id="1e70c-113">Вы также можете подключиться к [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) из Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-113">You can also connect with the [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) from the Microsoft 365 admin center.</span></span>
>


## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e70c-114">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="1e70c-114">What do you need to know before you begin?</span></span>


<span data-ttu-id="1e70c-115">**Операционная система**</span><span class="sxs-lookup"><span data-stu-id="1e70c-115">**Operating system**</span></span>

<span data-ttu-id="1e70c-p103">Необходимо использовать 64-разрядную версию Windows. Поддержка 32-разрядной версии модуля Microsoft Azure Active Directory для Windows PowerShell прекращена с 2014 г.</span><span class="sxs-lookup"><span data-stu-id="1e70c-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="1e70c-118">Ниже приведены версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="1e70c-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="1e70c-119">Windows 10, Windows 8.1, Windows 8 или Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="1e70c-119">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="1e70c-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="1e70c-120">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="1e70c-121">Для Windows 8.1, Windows 8, Windows 7 с пакетом обновления 1 (SP1), Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2 SP1 скачайте и установите [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="1e70c-121">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="1e70c-122">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1e70c-122">**PowerShell**</span></span>

- <span data-ttu-id="1e70c-123">Для модуля Azure Active Directory PowerShell для Graph требуется использовать PowerShell версии 5.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="1e70c-123">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="1e70c-p104">Для модуля Microsoft Azure Active Directory для Windows PowerShell требуется использовать PowerShell версии от 5.1 до 6. Использовать PowerShell версии 7 невозможно.</span><span class="sxs-lookup"><span data-stu-id="1e70c-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="1e70c-126">Эти процедуры предназначены для пользователей, которым назначена роль администраторов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-126">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="1e70c-127">Дополнительные сведения см. в статье [О ролях администраторов](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1e70c-127">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1e70c-128">Подключение к модулю Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="1e70c-128">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1e70c-129">Имена командлетов в модуле Azure Active Directory PowerShell для Graph включают компонент *AzureAD*.</span><span class="sxs-lookup"><span data-stu-id="1e70c-129">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="1e70c-130">Вы можете установить модуль [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2) или [Azure PowerShell](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="1e70c-130">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="1e70c-131">Если процедурам требуются новые командлеты в модуле PowerShell Azure Active Directory для Graph, выполните эти действия, чтобы установить этот модуль и подключить его к вашей подписке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-131">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="1e70c-132">Сведения о поддержке различных версий Windows см. в статье [модуль Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2) .</span><span class="sxs-lookup"><span data-stu-id="1e70c-132">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="1e70c-133">Шаг 1. Установите необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="1e70c-133">Step 1: Install the required software</span></span>

<span data-ttu-id="1e70c-134">Перечисленные действия необходимо выполнить на компьютере только один раз.</span><span class="sxs-lookup"><span data-stu-id="1e70c-134">These steps are required only one time on your computer.</span></span> <span data-ttu-id="1e70c-135">При этом, вероятно, потребуется регулярно обновлять программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="1e70c-135">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="1e70c-136">Откройте командную строку Windows PowerShell с повышенными правами (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="1e70c-136">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="1e70c-137">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1e70c-137">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="1e70c-138">По умолчанию галерея PowerShell (PSGallery) не настроена как доверенный репозиторий для **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-138">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="1e70c-139">При первом использовании PSGallery вы увидите следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="1e70c-139">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="1e70c-140">Чтобы продолжить установку, ответьте **Да** или **Да для всех**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-140">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="1e70c-141">Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-141">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="1e70c-p109">Чтобы установить подключение к Azure AD для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell (повышенные права не требуются).</span><span class="sxs-lookup"><span data-stu-id="1e70c-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="1e70c-144">Облачная служба Office 365</span><span class="sxs-lookup"><span data-stu-id="1e70c-144">Office 365 cloud</span></span> | <span data-ttu-id="1e70c-145">Команда</span><span class="sxs-lookup"><span data-stu-id="1e70c-145">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="1e70c-146">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="1e70c-146">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="1e70c-147">Office 365, предоставляемый 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="1e70c-147">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="1e70c-148">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1e70c-148">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="1e70c-149">Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="1e70c-149">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="1e70c-150">В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-150">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="1e70c-151">Если используется многофакторная проверка подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.</span><span class="sxs-lookup"><span data-stu-id="1e70c-151">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="1e70c-152">После подключения можно использовать командлеты для [модуля Azure Active Directory PowerShell для Graph](/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="1e70c-152">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1e70c-153">Подключение к модулю Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e70c-153">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="1e70c-154">Имена командлетов в модуле Microsoft Azure Active Directory для Windows PowerShell содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="1e70c-154">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="1e70c-155">В PowerShell версии 7 и более поздних версиях не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="1e70c-155">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1e70c-156">Для PowerShell версии 7 и более поздних версий требуется использовать модуль Azure Active Directory PowerShell для Graph или Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e70c-156">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="1e70c-157">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="1e70c-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1e70c-158">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e70c-158">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="1e70c-159">Шаг 1. Установите необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="1e70c-159">Step 1: Install the required software</span></span>

<span data-ttu-id="1e70c-160">Перечисленные действия необходимо выполнить на компьютере только один раз.</span><span class="sxs-lookup"><span data-stu-id="1e70c-160">These steps are required only one time on your computer.</span></span> <span data-ttu-id="1e70c-161">При этом, вероятно, потребуется регулярно обновлять программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="1e70c-161">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="1e70c-162">Если вы не используете операционную систему Windows 10, установите 64-разрядную версию помощника по входу в Microsoft Online Services. См. статью [Помощник по входу в Microsoft Online Services для ИТ-специалистов, RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="1e70c-162">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="1e70c-163">Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1e70c-163">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="1e70c-164">Откройте командную строку Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="1e70c-164">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="1e70c-165">Выполните команду **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-165">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="1e70c-166">Если будет предложено установить поставщик NuGet, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1e70c-166">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="1e70c-167">Если будет предложено установить модуль из PSGallery, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="1e70c-167">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="1e70c-168">Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-168">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="1e70c-p113">Чтобы установить подключение к Azure AD для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell (повышенные права не требуются).</span><span class="sxs-lookup"><span data-stu-id="1e70c-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="1e70c-171">Облачная служба Office 365</span><span class="sxs-lookup"><span data-stu-id="1e70c-171">Office 365 cloud</span></span> | <span data-ttu-id="1e70c-172">Команда</span><span class="sxs-lookup"><span data-stu-id="1e70c-172">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="1e70c-173">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="1e70c-173">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="1e70c-174">Office 365, предоставляемый 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="1e70c-174">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="1e70c-175">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1e70c-175">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="1e70c-176">Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="1e70c-176">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="1e70c-177">В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-177">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="1e70c-178">Если используется многофакторная проверка подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.</span><span class="sxs-lookup"><span data-stu-id="1e70c-178">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="1e70c-179">Как узнать, что все прошло успешно?</span><span class="sxs-lookup"><span data-stu-id="1e70c-179">How do you know it worked?</span></span>

<span data-ttu-id="1e70c-180">Если нет сообщений об ошибках, подключение успешно установлено.</span><span class="sxs-lookup"><span data-stu-id="1e70c-180">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="1e70c-181">Для проверки запустите любой командлет Microsoft 365, например **Get-MsolUser**, и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="1e70c-181">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="1e70c-182">Если появится сообщение об ошибке, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="1e70c-182">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="1e70c-183">**Распространенная проблема: неправильный пароль**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-183">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="1e70c-184">Повторите [шаг 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription), внимательно проверив имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="1e70c-184">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="1e70c-185">**Для работы модуля Microsoft Azure Active Directory для Windows PowerShell необходимо, чтобы на вашем компьютере был включен компонент Microsoft .NET Framework 3.5.* x*. Скорее всего, на вашем компьютере установлена более новая версия этого компонента (например, 4 или 4.5.\* x\*).</span><span class="sxs-lookup"><span data-stu-id="1e70c-185">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="1e70c-186">При этом можно включить или отключить режим обратной совместимости с более ранними версиями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e70c-186">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="1e70c-187">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="1e70c-187">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="1e70c-188">Windows Server 2012 или Windows Server 2012 R2: см. статью [Включение .NET Framework 3.5 с помощью мастера добавления ролей и функций](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="1e70c-188">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="1e70c-189">Windows 7 или Windows Server 2008 R2: см. статью [Не удается открыть модуль Azure Active Directory для Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e70c-189">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="1e70c-190">Windows 10, Windows 8.1 и Windows 8: см. статью [Установка .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="1e70c-190">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="1e70c-191">**Возможно, ваша версия модуля Microsoft Azure Active Directory для Windows PowerShell устарела.**</span><span class="sxs-lookup"><span data-stu-id="1e70c-191">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="1e70c-192">Чтобы проверить, выполните следующую команду в PowerShell для Microsoft 365 или в модуле Microsoft Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1e70c-192">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="1e70c-193">Если возвращенный номер версии меньше *1.0.8070.2*, удалите модуль Microsoft Azure Active Directory для Windows PowerShell и выполните установку с [шага 1](#step-1-install-the-required-software), описанного выше.</span><span class="sxs-lookup"><span data-stu-id="1e70c-193">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="1e70c-194">**Если появится сообщение об ошибке подключение**, см. статью [Ошибка "Connect-MsolService: исключение типа"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="1e70c-194">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="1e70c-195">**Если появляется сообщение об ошибке "Get-Item: не удается найти путь"**, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1e70c-195">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a><span data-ttu-id="1e70c-196">Подключение с использованием Azure Cloud Shell</span><span class="sxs-lookup"><span data-stu-id="1e70c-196">Connect with the Azure Cloud Shell</span></span>

<span data-ttu-id="1e70c-197">Чтобы подключиться с использованием Azure Cloud Shell из Центра администрирования Microsoft 365, щелкните значок окна PowerShell в правом верхнем углу панели задач.</span><span class="sxs-lookup"><span data-stu-id="1e70c-197">To connect with and use the Azure Cloud Shell from the Microsoft 365 admin center, select the PowerShell window icon from the upper-right corner of the task bar.</span></span> <span data-ttu-id="1e70c-198">В области **приветствия в Azure Cloud Shell** выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1e70c-198">In the **Welcome to Azure Cloud Shell** pane, select **PowerShell**.</span></span>

<span data-ttu-id="1e70c-199">Вам потребуется активная подписка Azure для организации, привязанная к вашей подписке на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e70c-199">You will need an active Azure subscription for your organization that is tied to your Microsoft 365 subscription.</span></span> <span data-ttu-id="1e70c-200">Если у вас ее нет, вы можете ее создать.</span><span class="sxs-lookup"><span data-stu-id="1e70c-200">If you don't already have one, you can create one.</span></span> <span data-ttu-id="1e70c-201">После получения подписки Azure откроется окно PowerShell, в котором можно запускать команды и сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e70c-201">Once you have an Azure subscription, a PowerShell window opens from which you can run PowerShell commands and scripts.</span></span>

<span data-ttu-id="1e70c-202">Дополнительные сведения см. в статье [Azure Cloud Shell](/azure/cloud-shell/overview).</span><span class="sxs-lookup"><span data-stu-id="1e70c-202">For more information, see [Azure Cloud Shell](/azure/cloud-shell/overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e70c-203">См. также</span><span class="sxs-lookup"><span data-stu-id="1e70c-203">See also</span></span>

- [<span data-ttu-id="1e70c-204">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e70c-204">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1e70c-205">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e70c-205">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1e70c-206">Подключение ко всем службам Microsoft 365 в одном окне Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e70c-206">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
